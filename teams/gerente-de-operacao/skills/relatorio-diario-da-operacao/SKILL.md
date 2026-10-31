---
name: relatorio-diario-da-operacao
description: "Montar o relatório da manhã da operação: o que precisa da pessoa, o que vence, as pendências de cada peça (capa, legenda, editor, data), os bots parados e o que está agendado. Use quando pedirem 'bom dia', 'como está a operação', 'relatório', 'pendências' ou quando a automação diária disparar."
---

# Relatório diário da operação

Uma leitura curta, que a pessoa entende em um minuto, do que está acontecendo e do que depende dela.

## Quando usar

- A pessoa diz "bom dia", "como está a operação", "o que tem pendente", "faz o relatório".
- A automação da manhã dispara (veja `coordenacao-recorrente-entre-bots` para criá-la).

## De onde vêm os dados

O quadro de status (`operacao/status.md`), o agendador de redes sociais conectado (grade de posts), o gerenciador de tarefas, o e-mail e a agenda, conforme o que estiver conectado. Se uma fonte não estiver conectada, escreva uma linha: "Não consegui ver X. Para ver, conecte em Apps conectados". Não invente e não preencha com o que você lembra.

## Estrutura

1. **Precisa de você:** aprovações paradas, decisões, gastos aguardando ok, perguntas abertas. Uma linha cada, com o que está esperando e desde quando.
2. **Vence hoje e nesta semana:** peça, cliente, prazo, responsável.
3. **Pendências por peça:** o que falta em cada item enviado para aprovação (capa, legenda, editor, data), uma linha por item, agrupado por cliente. É a lista para a equipe completar.
4. **Bots parados ou com falha:** quem não respondeu, o que ficou travado e o que você já fez.
5. **Agendado para hoje:** o que vai ao ar e quando.

Itens vazios saem do relatório: não escreva "nada" em seção sem conteúdo.

## Formato

Mensagem curta, em português do Brasil, sem travessão, sem tabela grande. Cada item cabe numa linha: "Cliente, peça: o que falta, com quem". A primeira seção fica no topo. O relatório inteiro cabe numa tela; se passar disso, mande o resumo e anexe o documento completo.

## Cuidados

- Não misture clientes: uma seção por marca, sem dado de uma na outra.
- Só relate o que foi visto numa fonte; o que foi inferido vai marcado como "a confirmar".
- Item concluído não repete no dia seguinte.
- Pedido de relatório fora do horário usa o mesmo formato e a data de agora.

## Antes de entregar

Todas as pendências citadas existem no quadro ou na fonte conectada, e cada item que depende da pessoa diz o que ela precisa fazer.
