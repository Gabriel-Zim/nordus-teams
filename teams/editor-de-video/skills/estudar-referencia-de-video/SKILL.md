---
name: estudar-referencia-de-video
description: "Baixar e analisar um vídeo de referência quadro a quadro para copiar a técnica com precisão: folhas de contato com tempo, tiras de transição no fps nativo, transcrição com tempo, medição de loudness e quebra escrita em ritmo, linguagem visual, tipografia, transições, câmera e som, com números. Use quando a pessoa mandar um link ou arquivo e pedir para estudar, igualar ou usar como referência."
---

# Estudar uma referência em detalhes

Referência é especificação, não inspiração. O resultado do estudo é uma análise tão precisa que dá para refazer a técnica em outro vídeo sem ver o original de novo.

## Quando usar

A pessoa manda um link (Instagram, YouTube, TikTok) ou um arquivo e pede "estuda como referência", "estuda em detalhes", "faz igual" ou "baixa esse vídeo e analisa". Também em todo pedido de vídeo que traz referência.

## Procedimento

1. **Pasta limpa e download.** Crie `refs/<nome>/` e baixe com `yt-dlp -f "bv*+ba/b" --merge-output-format mp4 -o "ref.%(ext)s" "<URL>"`. Se o link não baixar, tente pelo navegador e por outro caminho antes de dizer que não deu.
2. **Folhas de contato.** Com ffmpeg, amostre um quadro a cada 0,5 s (`fps=2`) e componha folhas com vários quadros por imagem, cada um com o tempo gravado. Olhe a progressão visual inteira.
3. **Tiras de transição.** Identifique os momentos em que a técnica muda (corte, wipe, morph, movimento de câmera). Em cada um, extraia de 5 a 10 quadros consecutivos no fps nativo, em resolução cheia, e alinhe lado a lado para ver a progressão quadro a quadro.
4. **Transcrição.** Extraia o áudio, transcreva com tempo por frase e anote música, efeitos e onde cada um entra na linha do tempo.
5. **Loudness.** Rode o filtro `ebur128` do ffmpeg no vídeo inteiro e registre o integrado (LUFS), o de curto prazo, o pico e a faixa de loudness. Anote o padrão seguido (para Reels, em torno de -14 LUFS).
6. **Cores e medidas.** Pegue em hex as cores dominantes e medidas em pixels dos elementos que importam (tamanho da palavra grande, margens, largura de faixa).
7. **Quebra escrita**, com números:
   - **Ritmo:** número de cortes, duração média do plano ("17 cortes em 27 segundos, 0,8 s por plano").
   - **Linguagem visual:** cores, tipo de objeto, tratamento ("fotos recortadas em preto e branco com retícula, só rostos coloridos").
   - **Tipografia:** famílias, tamanhos, hierarquia, animação do texto.
   - **Transições:** uma linha por transição, com duração em segundos e técnica ("faixa ondulada atravessa e abre em 1,0 s").
   - **Câmera e movimento:** empurrões, camadas de profundidade, paralaxe, passagens de luz.
   - **Som:** origem da música, proporção voz e música, efeitos e seus tempos, loudness.
8. **Entrega do estudo.** Salve em `refs/ANALISE.md` e anexe à conversa as folhas, as tiras e o resumo escrito, quando a pessoa pediu o estudo. Quando for só parte de um pedido, o estudo fica na pasta e orienta o plano.

## Cuidados

- **Navegador não lê arquivo local.** Para renderizar uma página HTML local, sirva a pasta por HTTP (`python3 -m http.server`) em vez de abrir `file://`.
- **Primeiro quadro com navegador frio sai vazio ou atrasado.** Espere a página assentar (1 a 2 s) ou descarte o primeiro quadro e repita.
- **Esquecer o áudio.** Loudness, pico e padrão fazem parte da receita. Sempre meça.
- **Descrição vaga.** "A faixa se abre" não serve. Escreva "faixa vermelha atravessa o rosto e abre em 0,5 s, revelando o rosto em gravura, câmera empurra".
- **Imagem de pessoa real ou de marca** que aparece na referência não vai para o seu vídeo sem origem clara e licença.

## Antes de dar por terminado

Há folhas com tempo, tiras com a duração de cada transição, transcrição com tempo, medidas de áudio e a quebra escrita cobrindo ritmo, linguagem visual, tipografia, transições (em segundos), câmera e som. Cada item está rotulado e específico o bastante para ser replicado.
