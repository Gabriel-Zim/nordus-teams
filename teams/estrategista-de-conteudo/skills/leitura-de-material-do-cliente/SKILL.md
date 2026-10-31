---
name: leitura-de-material-do-cliente
description: "Enxergar o material do cliente antes de planejar: catalogar a pasta ou o link (vídeos, fotos, planilhas), tirar quadros e folhas de contato, transcrever a fala, escolher trechos olhando os quadros e cruzando com o que é dito, e responder em uma mensagem curta, vídeo a vídeo, com o melhor trecho e o que não presta. Use quando chegar uma pasta, um link de armazenamento, vídeos ou fotos do cliente, e sempre antes de planejar um reel com material dele."
---

# Leitura do material do cliente

Quando chega material, você enxerga antes de planejar. **Nunca planeje reel com material do cliente sem ter olhado o material.**

## Procedimento

1. **Catalogue.** Liste tudo que chegou (pasta ou link). Para link de armazenamento em nuvem, use o conector da pessoa; se não houver acesso, peça que compartilhem a pasta com a conta conectada, em vez de abrir pelo navegador. Pasta grande: rode em segundo plano e avise numa linha ("Lendo 11 vídeos e 14 fotos, volto em cerca de 5 min").
2. **Vídeos.** Para cada um: duração, resolução, orientação (`ffprobe`), transcrição com tempo (modelo de fala local ou o que estiver conectado) e uma folha de contato com um quadro a cada 3 segundos (`ffmpeg -i video -vf fps=1/3,scale=320:-1,tile=6x...`). Olhe os quadros e cruze com a fala.
3. **Fotos e documentos.** Faça um mosaico das fotos (com o nome do arquivo em cada uma) e leia planilhas e textos que vieram junto.
4. **Escreva o catálogo** (`catalogo.md` na pasta da marca): arquivo, quem fala, onde, o que mostra, o que presta e o que não presta (tremido, vento, falso começo, ruído) e o melhor trecho com timecode de entrada e saída.
5. **Escolha trechos olhando os quadros**, não só pela transcrição.

## Como responder

Resposta de material lido, curta, em uma mensagem:

- Linha 1: o que chegou ("11 vídeos, 14 fotos, 1 planilha").
- Vídeo a vídeo, uma linha cada: quem fala, onde, o que mostra, o que presta e o que não presta (melhor trecho com timecode).
- Anexe o mosaico.

Depois siga a skill `estrategia-de-conteudo-para-redes` e diga, no topo da estratégia, quanto do material cobre cada ideia ("7 de 9 cenas com material").
