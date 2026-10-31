---
name: animacao-explicativa
description: "Vídeo vertical que explica qualquer assunto sem ninguém gravar: roteiro em estrutura fixa (gancho comparativo, jeito comum, reviravolta, mecanismo em 3 ou 4 telas, metáfora, pergunta final), narração gravada uma vez com tempo por palavra, personagem 3D que atua a fala e interage com a cena, títulos em serifa com palavra-chave em itálico, telas de interface, transições de marca, câmera viva, foley sincronizado e render em pedaços paralelos. Use quando pedirem animação explicativa, vídeo com boneco, 'explica X com animação' ou mandarem um roteiro para virar animação."
---

# Animação explicativa

Vídeo vertical que explica um assunto com narração, um personagem 3D que atua a fala e interage de verdade com a cena (toca, pega, carimba, bate palma), títulos editoriais, telas de interface e foley premium. Ninguém precisa gravar.

## Visual

Fundo claro e quente, títulos em serifa com a palavra-chave em itálico na cor de destaque da marca, telas de interface (janela, bolhas de conversa, rede, checklist, celular 3D, crachá 3D), transição de marca a cada 3 a 6 s e câmera sempre viva. O personagem é 3D ao vivo, na mesma luz e sombra dos objetos 3D da cena: nunca sprites nem imagem recortada animada.

## Passo a passo

1. **Pasta do pedido** com uma cópia do projeto-base de animação (HyperFrames ou Remotion com three.js, fontes, modelos 3D do personagem e do celular). Se o computador não tiver um kit pronto, monte o mínimo antes: cena base, personagem, celular, crachá e a paleta da marca.
2. **Roteiro** na estrutura: gancho comparativo, o jeito comum, a reviravolta, o mecanismo em 3 ou 4 telas, uma metáfora, a pergunta final. Frases curtas. Nada inventado. Amostra de demonstração fecha em no máximo 10 s, com assinatura e logo no fim.
3. **Narração uma vez só** (voz da marca ou da pessoa), com o tempo de cada palavra em `palavras.json`, no formato `[{p, i, f}]`.
4. **Decupe cada frase:** a tela, o gesto do personagem e ONDE ELE INTERAGE com a cena (toca o botão, pega a prancheta, carimba, é empurrado, bate palma). **Personagem parado ao lado da tela é o erro clássico**: reprova a peça.
5. **Escreva as cenas e a agenda do personagem.** Cada elemento entra na palavra em que é dito. A agenda do personagem usa gestos nomeados (parado, acena, pensa, aponta, comemora, pulo, corre, prancheta, espanto, pulo para tocar), com ajustes finos de olhar, giro, mão e pulo. Para um cliente, troque só a paleta e as fontes da ficha dele; o kit, os movimentos e a luz ficam iguais.
6. **Quadros soltos de cada cena.** Olhe e corrija o feio: volume, sombra no chão, contato real entre mão e objeto. Sirva a página por servidor local (`python3 -m http.server`), porque o navegador não abre arquivo local direto, e espere a página assentar antes de disparar os quadros: o primeiro disparo pega o navegador frio e sai vazio ou atrasado.
7. **Render em pedaços paralelos** (dezenas de pedaços numa GPU alugada ou em todos os núcleos locais) e junte na volta. Prefira o caminho que estimar mais rápido; falhou a GPU alugada, volte ao local e conte no relatório. Acabamento: desfoque de movimento de 4 quadros para 30 fps, vinheta leve, grão leve, H.264 em duas passadas com taxa alta.
8. **Som.** Voz, trilha leve da Epidemic Sound (cerca de 20 dB abaixo da voz) e cues de foley no tempo exato de cada gesto: whoosh, carimbo e palmas com o pico alinhado ao gesto. Efeitos em -13 dBFS antes do ganho; final em -14 LUFS e pico em -1 dB. Nunca efeito genérico de pacote; faltou um som específico, procure na biblioteca licenciada e guarde na biblioteca do projeto.
9. **Confira quadros e volume no arquivo final** e entregue anexado: "Segue. Aprova ou quer ajuste?". Ajuste só de som: remixe e junte ao vídeo pronto copiando a imagem, sem renderizar.

## Cuidados

- Esconda a legenda no fim de cada janela de fala; sem isso as palavras se acumulam e o fecho vira um bloco ilegível.
- Camadas da cena anterior podem continuar visíveis por baixo do fecho: desligue-as e confira o fecho quadro a quadro antes de renderizar.
- Logo branco sobre sol cobre fica lavado: leve o logo para o chão escuro e suavize o brilho até ele ficar nítido.
- Antes de refazer um render por causa de um objeto estranho, olhe o quadro em resolução cheia: muitas vezes é uma letra da legenda ou sobra de outra camada, não defeito do render.
- Sigla ditada letra por letra na narração deve sair na legenda com o nome certo da marca; ajuste antes de gerar as cenas.

## Tempo (referência)

Com render distribuído em GPU alugada, 24 s de vídeo levam cerca de 2 min de render e 60 s cerca de 6 min; no computador local o mesmo trabalho leva de 4 a 5 vezes mais. O grosso do tempo de um vídeo completo fica na decupagem e na montagem das cenas (algumas horas); um kit de cenas prontas reduz isso pela metade.

## Antes de entregar

Nos últimos 2 s do arquivo: legenda sem acúmulo, nenhuma camada da cena anterior, logo nítido sobre fundo escuro e assinatura no tempo da fala final. Volume em -14 LUFS com pico em -1 dB.
