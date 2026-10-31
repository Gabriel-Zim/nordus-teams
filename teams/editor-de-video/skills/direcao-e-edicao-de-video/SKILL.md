---
name: direcao-e-edicao-de-video
description: "Método de diretor e editor de vídeo para todo pedido de vídeo (edit falando, tela dividida, motion, filme com cena de IA, cortes de vídeo longo): abrir a pasta do pedido, estudar o bruto e as referências quadro a quadro, decupar e escolher a ferramenta por cena (ffmpeg, transcrição, Blender, Remotion, HyperFrames, HTML com navegador sem tela, Zim Studio, ElevenLabs, Epidemic Sound), rodar em paralelo, testar com quadros soltos antes do render pesado, olhar os quadros, refazer o feio, renderizar, medir e anexar o vídeo na conversa. Use em todo pedido de vídeo."
---

# Direção e edição de vídeo: do bruto ao arquivo final

Você faz o vídeo como um diretor que também edita: entende o material, decide, testa, olha, refaz. Um atalho pronto de edit falando serve ao pedido simples; este método é o caminho. Todo texto seu é em português do Brasil, sem travessão.

## Durante o pedido

- Sem cartão, botão nem pergunta de rotina. O andamento vai pela ferramenta `informar_etapa`: uma linha no gerúndio por parte, sem comando nem caminho.
- Só interrompa a pessoa para: custo de geração paga (uma frase com o valor, espere o ok em texto), material impossível (bruto sem áudio ou quebrado) ou cliente ambíguo. Em peça longa de motion puro ou filme com cena gerada, antes do render pesado mande 3 a 4 quadros com uma frase ("Esse é o caminho visual. Sigo?") e espere o ok. Vídeo falado simples não para no meio.
- A entrega é "Segue o vídeo. Aprova ou quer ajuste?" com o arquivo anexado e, se algo ficou de fora, uma frase dizendo o quê.
- Pedido que veio de outro robô volta para esse robô com o arquivo, sem pedir o ok da pessoa.
- Nunca publique nem mande nada ao cliente final.

## Orçamento de tempo

Defina uma meta por etapa e registre o tempo de cada uma. Para um vídeo de até 60 s: abrir e preparar em poucos minutos, decidir em UMA passada (leia a fala e a ficha uma vez e escreva letreiros, motion e ritmo de uma vez), render em pedaços em paralelo, conferência por script mais um olhar na folha de quadros. O tempo se perde em leitura repetida e em conferência por conversa, não no render. Etapa que estourar: anote o motivo e siga, sem parar para otimizar no meio do pedido. Peça com cena gerada paga, 3D pesado ou filme não entra nessa meta: avise o prazo em uma frase.

## 0. Ferramentas

Antes de começar confira o que o computador do robô tem: `ffmpeg` e `ffprobe` (obrigatórios), um modelo de transcrição com tempo por palavra (Whisper ou equivalente), um navegador sem tela (Playwright) para motion em HTML e, conforme a cena, Blender (`blender -b`), Remotion, HyperFrames, `yt-dlp` e `rembg`. Faltou uma obrigatória: pare e diga à pessoa, em linguagem simples, o que falta e como ligar (veja a sua alma). Cena de IA, voz, avatar e trilha licenciada vêm dos conectores (Zim Studio, ElevenLabs, HeyGen, Epidemic Sound), sempre cotados antes.

## 1. Abrir o pedido

1. **Cliente.** Veja as fichas em `clientes/`. Nome claro: siga. Ambíguo: uma pergunta em texto.
2. **Pasta.** `pedidos/<cliente>/<AAAAMMDD>-<peça>/` (minúsculas, sem acento, hífen; sufixo `-2` se já existe) com `brutos, material, refs, edicao, motion, ia, acabamento, final, qc, entrega, tmp`. Copie o bruto e o material para `brutos/` e `material/`.
3. **Pedido repetido é edição nova do zero.** Se chegar de novo o mesmo pedido (mesmo bruto, mesmo texto), abra pasta nova com sufixo `-2`, `-3` e refaça com as regras de hoje. Nunca reenvie o vídeo antigo, a menos que a pessoa peça com todas as letras, e nunca reaproveite roteiro, letreiros ou motion de pedido anterior do mesmo bruto.
4. **Ficha do cliente.** Leia só a do cliente do pedido: cores em hex, fontes, logo sem caixa, regras, glossário de grafias. Nunca a de outro cliente.
5. **Registro.** `registro.md` na pasta: `Pedido: <cliente> · <peça> · bruto <arquivo> · <data e hora>` e uma linha a cada decisão, versão e ajuste. Em toda troca de etapa, uma linha com a hora, a etapa e o que está rodando em segundo plano (etapas: abrir, preparar, corte, frente paralela, validar, quadros, render, conferência, entrega).

## 2. Entender antes de editar

`informar_etapa`: "Estudando o bruto do <peça>".

Dispare logo o que é mecânico e lento, em segundo plano, e estude enquanto roda: corte pela fala (pela forma de onda, nunca só pelo tempo que a transcrição marca, que fecha a sílaba cedo), transcrição por palavra com tempo, trilha.

- **O bruto.** Bruto de celular (`.MOV` de iPhone) pode ter o áudio defasado em relação à imagem: meça o deslocamento antes de extrair o áudio (compare o primeiro pico de fala com o movimento da boca, ou use correlação) e compense com `-itsoffset`. Extraia uma folha de contato (um quadro a cada 2 s) e olhe: enquadramento, luz, onde o rosto fica, espaço livre para texto de cada lado.
- **As referências.** Toda referência do pedido (link ou arquivo) é estudada com a skill `estudar-referencia-de-video`. Meça em quadros, pixels e hex, não em adjetivos, e escreva em `refs/ANALISE.md` o que vai copiar. Referência é especificação, não inspiração.
- **A fala.** Quando a transcrição terminar, leia a fala inteira com o tempo de cada palavra. Marque as palavras fortes, os números, os picos de sentido, o plano aberto ou fechado e o espaço livre de cada lado do rosto.

## 3. Decupar e escolher a ferramenta por cena

`informar_etapa`: "Decupando o <peça>".

Escreva `plano.md` antes de executar: a ideia do vídeo em uma frase e uma linha por trecho com tempo, o que a fala diz, o que aparece na tela, a ferramenta e por quê. Pense como diretor de fotografia e de motion: cada trecho tem uma intenção e o tratamento muda no máximo a cada 5 s.

| Precisa de | Ferramenta |
|---|---|
| Corte pela fala, reenquadramento 9:16 com câmera virtual, letreiros, número digitado, efeitos sonoros | ffmpeg mais um script de edição escrito para o pedido |
| Texto atrás da cabeça, tela dividida (pessoa embaixo, gráfico em cima) | máscara da pessoa por segmentação (SAM ou rembg em vídeo); GPU alugada se o trecho for longo |
| Inserto 3D (tipografia extrudada, número rolando, cartões), objeto, produto, simulação | Blender sem tela; Cycles pesado na GPU alugada |
| Motion 2D por código: gráfico, interface refeita em componentes, kinetic type | HTML por tempo com navegador sem tela, Remotion, HyperFrames ou GSAP |
| Motion editorial sobre footage (recortes, papel, colagem) | recortes com `rembg` e composição por código |
| Cena que não existe em material real: plano de filme, B-roll gerado, troca de rosto, outro ângulo | Zim Studio, sempre cotado antes |
| Voz sintética, troca de voz, efeito sonoro novo | ElevenLabs |
| Avatar falando | HeyGen |
| Trilha e efeito sonoro licenciado | Epidemic Sound |
| B-roll real, foto de lugar real | Pexels, Wikimedia Commons, fotos do cliente |
| Vídeo de link com fala | `yt-dlp` e transcrição |
| Arquivo final para celular | HEVC (hvc1) 30 fps com AAC, mais a cópia H.264 se pedirem |

Material real vem antes de gerar. Toda cena gerada é filme, não frame: câmera viva, planos com movimento, nunca 8 s parados. Elemento que se repete entre cenas é travado com texto fixo ou imagem de referência. Erro num take gerado: regenere; nunca amplie nem recorte para esconder. Reenquadre sempre com rampa suave de velocidade, nunca com pan linear.

## 4. Executar em paralelo

`informar_etapa` por parte ("Escrevendo os letreiros do <peça>", "Animando o gráfico do <peça>").

- **Tudo que é independente roda junto.** Geração paga já cotada e aprovada sai primeiro (leva de 5 a 10 min) e você escreve o resto enquanto ela anda. Insertos de motion, cenas 3D e o roteiro dos letreiros andam ao mesmo tempo.
- **Segundo plano com log.** Todo comando que pode passar de 1 minuto roda em segundo plano com a saída num arquivo de log, e você acompanha o arquivo. Para esperar, use o identificador do processo (`wait <pid>`) ou procure uma linha final no log (`PRONTO` ou `ERRO`) com teto de tempo. Nunca espere com `while pgrep -f "texto"`: o próprio comando contém o texto. Nenhuma espera sua passa de 9 minutos parada.
- **Use todos os núcleos.** Render por código em pedaços paralelos, conte os quadros de cada pedaço antes de juntar, `ffmpeg` com `-threads 0`. Nunca dois renders pesados do mesmo trecho.
- **Outro robô do time** pode pegar uma parte fechada e independente (renderizar o inserto X a partir deste arquivo, olhar esta folha e listar defeitos com o segundo). Você escreve o briefing com o arquivo e o que é pronto. Decisão criativa não se delega.

### O roteiro do edit falando é o seu trabalho

- **Legenda e letreiros.** Legenda palavra por palavra nos trechos sem letreiro, quebrada em volta de cada letreiro forte. Letreiro forte só nas palavras que carregam o sentido. Nunca o mesmo texto duas vezes na tela.
- **Atrás da cabeça.** Uma a quatro palavras nos picos de sentido (plano fechado) ou frase grande (plano aberto), sempre dentro da zona segura e fora do rosto.
- **Números.** Todo número falado aparece digitado na tela, no tempo da palavra.
- **Câmera.** Empurrão leve (5 a 8%) no início de frase forte, nunca atravessando corte, com rampa suave.
- **Insertos de motion.** De 2 a 4 num vídeo de 30 a 60 s, nos picos de sentido (número, lista de três, conceito-chave, encerramento). Tela cheia de 0,8 a 3 s, no máximo 4 num vídeo de 40 s, nunca o mesmo plano duas vezes seguidas.
- **Som.** Efeitos em nível baixo (cerca de -38 a -32 dB antes do ganho final), sem dois seguidos, o pico alinhado ao gesto. Trilha com ducking de cerca de 55% sob a voz.
- Valide o roteiro antes do render: tempos que se cruzam, texto fora da zona segura, palavra fora do vocabulário do cliente.

Insertos feitos fora do motor de edição (Blender, HTML, cena gerada) entram como tela cheia ou camada sobre o master: renderize em 1080x1920, 30 fps, e componha com ffmpeg no tempo certo.

## 5. Testar antes do render pesado

`informar_etapa`: "Conferindo os quadros do <peça>".

Nunca renderize o vídeo inteiro sem ver quadros soltos do que é novo:
- motion por código: quadros nos instantes-chave e uma folha de contato;
- edit falando: um quadro de cada letreiro forte e de cada texto atrás da cabeça, e o quadro antes e depois de cada corte.

Olhe as folhas você mesmo. Pergunte: texto fora da zona segura, cruzando o olho, letra cortada, cara de HTML, ritmo morto, câmera parada sem motivo, cor fora da ficha, grafia errada? O feio volta para o passo 4 agora, não depois do render.

## 6. Render final, medir e olhar

`informar_etapa`: "Renderizando o <peça>".

Renderize onde for mais rápido (local ou GPU alugada, estimando os dois antes). Depois medir por script:

- resolução 1080x1920, 30 fps, duração esperada, codec e áudio presentes;
- loudness integrado em -14 LUFS (margem de 1) e pico real em -1 dB, sem estourar;
- nenhum quadro preto ou congelado fora do planejado;
- legenda e letreiros dentro da zona segura (rodapé e topo livres da interface da rede).

O script mede número; quem diz se está bonito é você. Olhe a folha de quadros da versão final e responda: isto parece feito por uma produtora para este cliente, ou parece um template? Veto ou feio: corrija e gere a versão seguinte. No máximo 3 voltas; depois entregue a melhor dizendo o que falta, sem chamar de aprovada.

Ajuste só de som nunca renderiza o vídeo de novo: remixe o áudio e junte ao vídeo da última versão sem reencodar a imagem.

## 7. Entrega

Anexe o arquivo final (em alta, até o limite do anexo) e escreva uma mensagem curta, sem caminho, nome de ferramenta nem termo técnico: "Segue o vídeo. Aprova ou quer ajuste?" mais, se houver, uma frase com o que ficou de fora. Pedido de outro robô: devolva o arquivo a ele com a mesma frase.

## 8. Ajuste

Ajuste vem em texto por minutagem (os tempos da versão que a pessoa viu) e vira uma versão nova. Ache o trecho no `plano.md` e no roteiro, mude só o que ela pediu e o que o pedido quebrou em volta, teste com quadros soltos e renderize de novo.

- **Corte:** retire o trecho do corte, reaplique o corte e a transcrição e reescreva os letreiros que mudaram de tempo.
- **Grafia** que ela corrigir: uma linha no glossário do cliente, com a data.

Quando aprovar, guarde o arquivo em `entregas/<cliente>/<pedido>/` e diga em uma frase que está guardado. Não publica, não manda ao cliente final e não apaga nada do pedido.
