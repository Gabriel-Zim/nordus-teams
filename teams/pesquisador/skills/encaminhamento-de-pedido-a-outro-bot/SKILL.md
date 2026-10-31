---
name: encaminhamento-de-pedido-a-outro-bot
description: "Mandar um item já escolhido a outro bot do time para produzir o entregável pedido (em geral a copy), fechando o pedido numa frase com o item, o entregável, a série de números permitida e o que fica de fora, e refazendo no mesmo bot com rework quando a volta vier no formato errado. Use quando pedirem 'manda para o estrategista', 'manda a ideia número N' ou 'pede a copy dessa'."
---

# Encaminhamento de pedido a outro bot

Manda um item já escolhido ao bot nomeado para ele produzir o entregável pedido, em geral a copy. Não pesquisa de novo, não desenha a peça e não publica.

## Quando usar

- "Manda para o estrategista", "para ele pensar uma copy".
- "Manda a número N", "a ideia número N".
- A volta do outro bot veio no formato errado e o pedido precisa ser refeito.

## Procedimento

1. **Não entre na fila do computador nem abra o navegador.** O envio é entre bots.
2. **Feche o pedido numa frase:** qual item (número e gancho), qual entregável (copy falada do vídeo ou copy de carrossel), qual série numérica pode entrar e o que fica de fora (placar, promessa, número que as fontes não fecharam).
3. **Chame `coordinate_bots`** com o bot destino (use `list_bots` para achar o estrategista de conteúdo do time) e esse texto como motivo. Anexe as fontes que você abriu.
4. **Avise a pessoa** que o pedido saiu e que a copy chega quando o outro bot responder. Não escreva a copy no lugar dele.
5. **Se a volta não for o entregável pedido**, chame `informar_etapa` com o que faltou e `coordinate_bots` de novo no mesmo bot, com `rework` e o motivo dizendo o formato que faltou. Não abra um pedido novo em paralelo.

## Cuidados

- **Não espere a fila do computador compartilhado** para mandar texto a outro bot. A fila segura quem está na tela, e o pedido fica parado enquanto a pessoa repete o envio.
- **Não mande motivo vago.** Sem formato, série permitida e exclusões, a volta vem em outro formato e o ciclo recomeça.
- **Não recomece do zero** quando só o formato voltou errado: `rework` no mesmo bot mantém o fio; um pedido paralelo duplica o trabalho.

## Antes de dar por terminado

`coordinate_bots` saiu para o bot nomeado com o motivo fechado, sem esperar fila do computador, e a pessoa foi avisada de que o pedido saiu.
