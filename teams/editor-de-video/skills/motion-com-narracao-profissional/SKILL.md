---
name: motion-com-narracao-profissional
description: "Produzir vídeo de motion para uma marca com narração de locutor (voz da biblioteca da ElevenLabs ou voz própria já aprovada), assets gerados ou oficiais, tipografia cinética, câmera viva, trilha e efeitos licenciados da Epidemic Sound e mixagem em -14 LUFS: confirmar a voz, gravar, desenhar 15 a 20 cenas amarradas ao tempo de cada palavra, testar quadros contra a referência, renderizar, mixar e conferir. Use quando pedirem vídeo de motion com locutor profissional, narração, voz de jornalista ou motion com a voz da pessoa."
---

# Motion com narração: voz, cenas, trilha e mixagem

Vídeo de motion para uma marca, com narração (locutor da biblioteca de vozes ou voz própria já aprovada), motion feito sob medida com a tipografia da marca, assets gerados quando não existem oficiais e áudio premium licenciado.

## Quando usar

A pessoa pede "faz um vídeo para <cliente> com locutor profissional", "narração profissional", "voz de jornalista", "motion com a minha voz" ou manda um roteiro para virar motion com narração.

## Procedimento

1. **Confirme quem narra** antes de gravar: "Quem narra: locutor profissional da biblioteca de vozes?" ou a voz própria aprovada. Voz errada muda o tom inteiro e gravar de novo custa tempo e crédito. Se for locutor, ofereça de 3 a 4 amostras do mesmo trecho curto, anexadas numa única mensagem, e espere a escolha.
2. **Grave a narração** uma vez só, no tempo-alvo (54 a 60 s num Reels). Voz própria aprovada: use as mesmas configurações da receita original, sem variar. Extraia o tempo de cada palavra em JSON `[{p: palavra, i: início_ms, f: fim_ms}]`. Esse arquivo é a fonte da verdade do tempo das cenas: erro de 50 ms se acumula de cena em cena.
3. **Prepare os assets.** Fotos oficiais, material da marca, fontes de domínio público (Wikimedia Commons para figuras públicas). Onde não houver asset, gere pelo Zim Studio (`gerar_imagem`), com o modelo escolhido de forma explícita, revisando o primeiro lote antes de gerar em massa (um prompt ruim gera lote inútil: acerte em 1 a 3 exemplos antes). Remova o fundo com `rembg` ou Pillow e confira recortes limpos. Organize em `assets/imagens/`.
4. **Defina o motor de animação** (HTML por tempo, Remotion, HyperFrames ou Blender, conforme a cena) com a tipografia e a paleta da marca como âncora visual. **A marca é guia, não jaula:** use cor e fonte para criar memória, mas eleve o motion além do conformismo estático, com tipografia cinética, câmera, desfoque de movimento e entradas por ângulos variados.
5. **Com referência:** estude-a com a skill `estudar-referencia-de-video` e trate-a como especificação. Replique tudo: cor, brilho, desfoque, tratamento de borda, tempo de cada transição, direção e velocidade da câmera, hierarquia tipográfica, profundidade de camadas, ritmo. Escreva na configuração das cenas os parâmetros medidos (largura do brilho em pixels, raio do desfoque, velocidade do pan em graus por quadro, duração da transição em milissegundos). Renderize quadros de 2 a 3 cenas-chave cedo e compare lado a lado com a referência no mesmo tempo. Diferiu (brilho fraco, pan lento, borda mole)? Ajuste os parâmetros e repita até casar. Não improvise variação: se há diferença, a especificação foi mal lida.
6. **Sem referência:** estilo documental editorial como base: tipografia cinética, câmera de empurrar e puxar, desfoque de movimento, entradas variadas, SFX nos momentos de animação.
7. **Desenhe as cenas (nos dois casos).** Divida o roteiro em 15 a 20 cenas (3 a 4 s cada num vídeo de 1 minuto; menos que isso fica estático, mais fica nervoso). Para cada cena defina assets, início e fim em segundos amarrados à voz, e o motion:
   - **tipografia cinética:** texto entrando pelos lados, movendo-se, transformando-se ou escalonado com a narração;
   - **câmera:** empurrão e recuo, travelling, paralaxe com profundidade;
   - **desfoque de movimento** nos elementos que se mexem;
   - **entradas em ângulos e tempos variados**, nunca tudo centrado e parado;
   - **camadas de profundidade:** primeiro plano, meio e fundo.
   Números, frases-chave e imagens entram junto com a palavra correspondente, ou um instante antes, com o tempo escrito na configuração (nada no olho).
8. **Renderize** as cenas em 30 fps, em pedaços paralelos, na GPU alugada se for mais rápido, senão local, e junte os quadros em sequência.
9. **Áudio licenciado.** Trilha: busque na Epidemic Sound música que combine com o tom da marca (`SearchRecordings`) e baixe (`DownloadRecording`). Efeitos: só da biblioteca premium (`SearchSoundEffects` e `DownloadSoundEffect`), um por momento de cena (impacto, transição, interface). Nunca efeito genérico de pacote nem amostra livre: a diferença se ouve na hora. Se o efeito certo não existe, procure mais antes de substituir.
10. **Mixagem.** Voz centrada em 0 dB de referência, sem ducking nem atraso. Trilha em cerca de -9,5 dB, com redução de 55% enquanto há fala. Efeitos entre -38 e -32 dB antes do ganho final, com o pico alinhado ao gesto (objeto que pousa, número que chega ao valor, texto que aparece), no máximo -1 dB de pico. Remixe os níveis antes de comprimir: comprimir primeiro endurece a mistura. Final: -14 LUFS integrados, pico real em -1 dB.
11. **Monte e confira.** Junte os quadros com a trilha, confira a sincronia nos momentos-chave (texto, números, transições) e a duração do roteiro. Segure o último quadro de 1 a 2 s.
12. **QC.** Assista inteiro e confira de 3 a 5 momentos: transições, texto e imagem sincronizados com a narração, tempo dos efeitos (precisão de 1 quadro), níveis de áudio, quadro final. Com referência, compare o vídeo final com ela nesses mesmos momentos.
13. **Entregue** anexando o MP4: "Segue o vídeo de <duração> com locutor profissional. Aprova ou quer ajuste?".

## Cuidados

- **Confirme a voz antes de gravar.** Voz errada refaz tudo.
- **Tempo de animação complexa vai na configuração, em milissegundos**, nunca estimado no olho.
- **Imagens de pessoa real** só de fonte oficial, domínio público ou licença confirmada.
- **Rigidez de marca sem riqueza de motion** gera vídeo estático e fraco. Marca é memória, não regra de enquadramento.
- **Referência é especificação.** Quem recebe uma referência e entrega uma variação criativa entendeu errado o pedido.
- **Quantidade de cenas:** 54 a 60 s pedem 15 a 20 cenas.

## Antes de entregar

MP4 com no máximo 1 min, 9:16, 30 fps; áudio em -14 LUFS e pico em -1 dB; texto e imagens sincronizados com a narração (checado em 3 a 5 momentos); efeitos sincronizados; sem quadro vazio nem falha nas transições; motion com tipografia cinética, câmera e desfoque de movimento, não apenas zoom e pan; marca reconhecível sem prender a animação; e, havendo referência, estilo (brilho, desfoque, câmera, tipografia, ritmo, borda) igual ao dela nos momentos conferidos.
