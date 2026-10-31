---
name: video-com-avatar-e-voz-sintetica
description: "Vídeo em que a pessoa não grava: roteiro curto, voz sintética da ElevenLabs, avatar no HeyGen, material real do assunto, motion em cima e avatar embaixo, legenda, trilha licenciada e entrega. Inclui a regra de aprovação de crédito (pedir o ok uma vez, com escopo e teto, e executar sem perguntar de novo) e a versão do mesmo vídeo em outro idioma com o mesmo avatar. Use quando pedirem vídeo com avatar, vídeo sem gravar, versão em outro idioma ou 'faz um Reels meu sobre X' sem bruto."
---

# Vídeo com avatar e voz sintética

A pessoa manda só o tema (ou a copy) e a duração. O resto é seu: roteiro, voz, avatar, material, edição e entrega. Vale a skill `direcao-e-edicao-de-video` (julgamento, paralelismo, quadros soltos, olhar a folha, registro com os tempos). Esta skill fixa o que é deste formato.

## Pré-requisitos

HeyGen (avatar) e ElevenLabs (voz) conectados. Se faltar um dos dois, pare antes de qualquer trabalho e explique como ligar (Apps conectados, aba Conexões avançadas), em vez de improvisar outro serviço. Trilha licenciada vem da Epidemic Sound; cena de IA, do Zim Studio, sempre cotada.

## Fixos do cliente (guarde na ficha dele)

Antes de começar, a ficha do cliente tem: a voz aprovada (id e modelo da ElevenLabs), o avatar aprovado (grupo e look no HeyGen, com a versão do motor), o perfil que aparece na tela (arroba, nome, cor de destaque) e o formato (1080x1920, 30 fps). Nenhum desses muda sem a pessoa. Avatares de outros clientes da conta nunca são usados.

## Regras do formato

- Nunca diga, na fala ou na tela, que é avatar, clone ou voz de IA, a menos que a pessoa peça.
- Sempre "você", nunca "tu", salvo a ficha do cliente dizer outra coisa.
- Sem travessão e sem emoji na fala, na tela e na legenda.
- A metade de cima da tela é gráfico, gravação de tela, interface, captura real ou motion do assunto. Nunca a frase repetida (a legenda já carrega a fala); no máximo um rótulo de 1 a 2 palavras ou um número.
- Design 2D forte: cor chapada, tipografia firme, uma base e um acento, sem carnaval.
- Explainer de app ou site: gravação real de alguém usando, com zoom enquadrando cada elemento inteiro e respiro, nada de print estático com texto de exemplo, nenhuma interface cortada.
- **Pronúncia:** escreva a fala em grafia fonética para a voz (sigla letra por letra, número por extenso, termo estrangeiro como se fala) e a legenda na grafia normal.

## Passo a passo (o que roda junto)

1. **Roteiro (2 a 4 min).** Duração pedida vezes cerca de 2,5 palavras por segundo (20 s ≈ 50 palavras; 60 s ≈ 150). Frases de 4 a 12 palavras, gancho nos 2 primeiros segundos, prova visual até 5 s e, quando fizer sentido, um fecho com chamada ("Comenta <PALAVRA> que eu te mando <coisa>"). Salve `fala.txt` (fonética, blocos separados por linha em branco), `legenda.txt` (grafia normal) e `tela.md` (o que aparece em cima em cada frase e o material necessário).
2. **Cote e peça o ok uma vez.** Diga o escopo (voz, avatar, o que é grátis e o que gasta), o custo estimado e o teto, em uma frase. Com o "pode", execute sem pedir de novo. Só pergunte outra vez se o custo passar do dobro do estimado ou o escopo mudar. Falha de ferramenta não é motivo para pedir outro ok: investigue, tente de novo e relate se não resolver. Passos grátis (envio de arquivo, cotação, preparação de material) começam na hora.
3. **Dispare junto, em segundo plano:**
   - **Voz:** gere a fala inteira com a voz e o modelo da ficha (ElevenLabs). Voz sem pausa entre blocos: abra de 0,25 a 0,4 s entre eles com ffmpeg (nunca regenere por isso).
   - **Material:** uma tarefa por item de `tela.md` que pede busca ou gravação: gravação real de site ou app, captura de página, foto real de lugar ou produto (Wikimedia Commons, Pexels, site oficial), logo vetorial oficial. Tudo em `material/` com a fonte anotada.
   - **Trilha:** busque na Epidemic Sound música instrumental com a energia certa e corte na duração exata da voz, com fade de entrada e saída.
4. **Avatar no HeyGen** (no segundo em que a voz existir). Suba o áudio (`create_asset_upload` e, depois do envio dos bytes com todos os cabeçalhos devolvidos, `complete_asset_upload`), peça o vídeo com `create_video_from_avatar` usando o avatar da ficha, o áudio enviado, a versão do motor da ficha, a proporção e a resolução (1080p), sem legenda. Acompanhe com `get_video` a cada 20 a 30 s sem refazer o pedido se demorar (18 s de fala levam em torno de 2 min) e baixe o arquivo.
5. **Enquanto o avatar gera, não espere parada.** Escreva as cenas do `tela.md` com o tempo nas palavras da legenda, grave as páginas reais que a cena de ferramenta vai usar, deixe a trilha cortada. Quando o avatar chegar: monte a tela dividida (se o quadro do avatar vier fechado demais para a legenda caber abaixo do queixo, estenda a base com uma faixa escura desfocada), faça o recorte da cabeça atravessando a emenda em segundo plano, confira as palavras da transcrição (ela erra termos estrangeiros e a palavra da chamada final) e corrija antes de montar a legenda.
6. **Quadros soltos antes do render** (depois do recorte): um quadro a cada 0,6 s numa folha de contato, e a lista de conferência de `direcao-e-edicao-de-video`. Corrija nas cenas.
7. **Som, render e conferência.** Mixe voz e trilha, renderize em pedaços paralelos, olhe a borda do cabelo e a legenda na folha final e exporte em HEVC 30 fps.
8. **Entrega** na conversa, com o vídeo anexado: "Segue o vídeo. Aprova ou quer ajuste?" e uma linha com a legenda sugerida do post (gancho na primeira linha, 3 a 5 hashtags, sem emoji, sem travessão). Nada vai a cliente final ou a publicação sem o ok.

## Mesmo vídeo em outro idioma

Mantenha o mesmo avatar (mesmo id), a mesma duração e o mesmo visual. Mude só a voz e o idioma, as telas e a legenda. Gere a voz no idioma pedido (inglês dos EUA quando disserem "inglês") e refaça o tempo das cenas nas palavras novas. Versão de idioma não é uma nova aprovação criativa: não pergunte de novo sobre visual, avatar ou crédito além do ok já dado.

## Custo

Gere voz e avatar uma vez só. Ajuste de corte, cena ou mixagem nunca refaz voz nem avatar. Se a fala precisar mudar, refaça só o bloco que mudou. Registre no relatório quanto gastou (caracteres de voz e segundos de avatar).
