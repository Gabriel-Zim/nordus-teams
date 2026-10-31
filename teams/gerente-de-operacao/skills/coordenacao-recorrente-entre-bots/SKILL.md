---
name: coordenacao-recorrente-entre-bots
description: "Montar automações que se repetem e envolvem mais de um bot: buscar um conteúdo em horário fixo, mandar ao bot que processa com a especificação completa, entregar o resultado e avisar a pessoa, mais lembretes repetidos até ela confirmar e a retomada quando o bot que processa falha em silêncio. Use quando pedirem 'toda semana', 'todo dia às X', 'me lembra até eu confirmar' ou quando um pedido delegado travar."
---

# Coordenação recorrente entre bots

Para tarefas que se repetem em horário fixo e passam por mais de um bot: buscar algo numa fonte, mandar a outro bot para processar e entregar o resultado pelos canais que a pessoa escolheu. Para a pessoa, isto se chama "automação".

## Quando usar

- "Toda quinta às 21h, pegue o último vídeo do canal e peça os cortes ao editor."
- "Me lembre a cada hora até eu dizer que fiz."
- Um bot recebeu o pedido e não confirmou a entrega.

## Criar a automação

1. **Crie com `create_trigger`.** Horário em cron (por exemplo `0 21 * * THU`) com fuso explícito (por exemplo `America/Sao_Paulo`). Sem o fuso, a automação roda no horário do servidor.
2. **Escreva as instruções como passos completos para uma execução futura**, que não vê esta conversa: onde buscar, o que extrair, como identificar o item certo (por exemplo, "o vídeo publicado no mesmo dia ou no dia anterior"), o que fazer se a fonte estiver vazia.
3. **Mande ao bot que processa com `coordinate_bots`** a especificação inteira: link do conteúdo, estilo, formato, onde entregar. O outro bot não adivinha.
4. **Salve o padrão com `memory_update`** (agenda, formato esperado), para que os próximos ciclos precisem de menos instrução.
5. **Entregue** em todos os canais combinados: arquivos na pasta combinada e aviso à pessoa com o link e o estado.
6. **Defina a retenção** antes de ativar (guardar os últimos N ou apagar depois de X dias); sem isso os arquivos se acumulam.
7. **Verifique o primeiro ciclo:** a automação disparou na hora local certa, o bot recebeu o pedido, a saída chegou no formato certo e a pessoa foi avisada.
8. **Desligue com `manage_trigger`** quando não for mais necessária e confirme à pessoa. Use `list_triggers` para revisar o que está ativo.

## Lembrete repetido até confirmar

1. Crie uma automação com janela de horário (por exemplo `0 8-21 * * FRI`, de hora em hora, das 8h às 21h), com fuso.
2. Entregue o lembrete em todos os canais combinados, com a descrição exata da tarefa, igual em todos.
3. Fique atento a qualquer mensagem de "feito" em qualquer canal.
4. Ao confirmar, desligue na hora e avise em todos os canais que os lembretes pararam. Não espere a pessoa pedir.

## Quando o bot que processa falha em silêncio

Se o pedido chegou ao bot e ele não confirma a entrega em 2 a 3 minutos (em tarefa curta):

1. **Confira o sistema de destino**: o item está agendado, o arquivo existe, o post saiu? Compare o que foi pedido com o que existe.
2. **Pedido recebido e saída ausente** quer dizer falha silenciosa. Não espere mais: reúna o material, faça o trabalho pelo caminho direto e atualize o estado do sistema.
3. **Avise o outro bot** com `coordinate_bots`: "Eu assumi, não repita. Já está em: link."
4. **Reporte à pessoa:** qual bot recebeu, por que falhou (hora do pedido, estado do sistema), o que você fez no lugar e o link da entrega.

Se a pessoa disser "agiliza" depois de delegar, o prazo mudou: assuma de imediato.

## Cuidados

- **Fuso errado:** teste o primeiro disparo e confira o horário.
- **Instrução vaga:** o bot que processa precisa de estilo, formato, entrega e qualidade no próprio pedido, não só do link.
- **Fonte indisponível:** se o conteúdo foi apagado ou não saiu, avise a pessoa na hora, não termine sem resultado.
- **Bot parado:** confirme que o bot está ativo antes de ligar a automação; se ele estiver fora, avise a pessoa em vez de enfileirar em silêncio.
- **Etapa intermediária desligada:** se uma automação do meio (por exemplo, a que repassa aprovados) estiver pausada, o pedido nunca chega ao bot e ele não tem como falhar. Confirme que a cadeia inteira está ativa antes de investigar o bot.
- **Tempo:** rode logo depois que o conteúdo é publicado, não dias depois.
- **Lembrete esquecido:** automação de lembrete continua para sempre se ninguém desligar. Desligue ao receber a confirmação.

## Antes de dar por terminado

A automação disparou na hora local esperada, o resultado apareceu no destino no formato certo, a pessoa foi avisada em todos os canais combinados e, no caso de lembrete, ele parou quando ela confirmou.
