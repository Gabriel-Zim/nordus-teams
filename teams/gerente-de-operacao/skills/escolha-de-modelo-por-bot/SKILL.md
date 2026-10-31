---
name: escolha-de-modelo-por-bot
description: "Escolher e aplicar o modelo de IA que cada bot do time usa: mapear o time, responder com uma tabela de bot por modelo com o nome exato do catálogo e a razão em uma frase, propor a troca pelas ferramentas do app e testar o bot depois. Use quando perguntarem 'qual o melhor modelo para cada bot', 'troca o modelo do X', 'dá para usar um modelo mais barato aqui' ou quando um bot ficar mudo."
---

# Escolha de modelo por bot

Escolhe qual modelo de IA cada bot do time usa e aplica a troca pelas ferramentas do app. Cobre o conselho (modelo por função, custo contra benefício) e a mudança em si. Não cobre as instruções do bot, os fluxos nem o conteúdo.

## Quando usar

- "Qual o melhor modelo para cada bot?", "dá para usar um modelo mais barato no X?", "troca o modelo do Y".
- Um bot ficou mudo porque o crédito do modelo acabou ou o modelo escolhido ficou indisponível.

## Procedimento

1. **Mapeie o time e os modelos atuais antes de responder**, com `list_team_setup` (visão do time) e `list_bots` (cada bot e o modelo em uso).
2. **Divida o time por tipo de tarefa.** Orquestração de contexto longo e julgamento (o líder, quem coordena) pede o modelo mais forte. Trabalho de rotina (status, agendamento, tarefas repetitivas) tolera um modelo rápido e barato. Bots criativos ou de render precisam do que a ferramenta deles exige.
3. **Responda com uma tabela de bot por modelo, com o nome exato como aparece no catálogo**, uma linha por bot e uma frase com a razão. Não responda em faixas ("barato", "rápido", "premium") nem com "depende": a pessoa vai perguntar de novo até aparecerem os nomes.
4. **Apresente custo contra benefício como o custo de uma execução errada**, não o preço do token: um modelo barato que erra o trabalho custa mais do que economizou. Diga com clareza quais funções podem ser rebaixadas e quais não.
5. **Aplique só nos bots sob a sua gestão.** Proponha cada troca com `propose_model`, agrupando as ligadas em `propose_team_setup`. Depois relate quais bots mudaram e quais a pessoa precisa mudar nos ajustes do próprio bot, por estarem fora da sua gestão.
6. **Teste o bot depois da troca** com um pedido pequeno. A troca só vale quando volta uma resposta.
7. **Bot mudo:** confira primeiro o modelo e o crédito. Recarregue a conta ou troque por um modelo disponível, depois teste de novo.

## Cuidados

- **Responder em faixas em vez de nomes** custa outra rodada: dê a tabela com nomes exatos na primeira resposta.
- **Prometer uma troca que você não pode fazer.** Bots fora da sua gestão são só leitura para você: nomeie-os e entregue a mudança à pessoa, sem insinuar que foi feita.
- **Rebaixar o orquestrador.** A coordenação de contexto longo é a primeira a piorar num modelo pequeno, mesmo quando as tarefas de rotina ainda parecem boas. Mantenha quem coordena no modelo forte.
- **Trocar sem testar.** Silêncio depois da troca costuma ser modelo indisponível ou crédito esgotado, não bot quebrado. Teste e corrija o modelo; não refaça o time inteiro.

## Antes de dar por terminado

Cada bot trocado respondeu a uma mensagem de teste, e `list_team_setup` ou `list_bots` mostram o modelo novo nos bots que mudaram.
