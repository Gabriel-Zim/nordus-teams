# GERENTE DE OPERAÇÃO

Gerente da operação que reparte cada pedido entre os bots do time, cobra prazos e pendências, faz o relatório diário e leva a você só o que depende de você.

## O que ele faz

Um gerente que coordena os outros bots do time: manda cada pedido a quem tem a função (designer, editor de vídeo, social media da marca, programador, atendimento, financeiro) com o briefing inteiro, acompanha prazo e status, assume quando um bot fica mudo e traz a você só aprovações, perguntas e falhas. Monta o relatório da manhã com o que precisa de você e as pendências de cada peça, cria automações recorrentes e lembretes, escolhe o modelo de IA de cada bot e resolve tarefas do dia a dia como cancelar uma assinatura, recuperar um domínio suspenso ou achar uma data no e-mail. Nada sai para fora sem o seu ok.

## O que você recebe

- Cada pedido chega ao bot certo com o briefing completo, e o status de todos os pedidos fica num quadro único.
- Relatório da manhã curto, com o que precisa de você no topo e uma linha por pendência (capa, legenda, editor, data).
- Automações recorrentes e lembretes até a confirmação, com retomada quando um bot trava em silêncio.

## Quem está no time

| Bot | Título | O que faz |
|---|---|---|
| GERENTE DE OPERAÇÃO (líder) | Gerente da operação | Reparte os pedidos entre os bots do time, acompanha prazo e status, faz o relatório diário e leva a você só aprovações, perguntas e falhas. |

O bot marcado como líder entra como **Boss** da seção nova: é quem fala com você e coordena os outros bots do modelo. Os demais entram como bots comuns.

## Antes de usar

Tempo para configurar: cerca de 10 minutos.

- **Os outros bots do time** (opcional): receber os pedidos que o gerente reparte (design, vídeo, conteúdo, código, atendimento, dinheiro).
  Como: adicione ao mesmo workspace os modelos que a sua operação usa (todos estão em Modelos, na barra lateral); sem um deles o gerente diz qual falta e não improvisa o trabalho.
- **E-mail, agenda e arquivos em nuvem** (opcional): ler prazos, achar fatos no e-mail e abrir pastas compartilhadas.
  Como: em Apps conectados, ligue o app da sua caixa de e-mail, da sua agenda e do seu armazenamento em nuvem e entre com a sua conta (depois ligue a chave Apps conectados do bot em Configurações → Acesso).
- **Gerenciador de tarefas e agendador de redes sociais** (opcional): ver o que vence e o que está agendado para entrar no relatório da manhã.
  Como: em Apps conectados, ligue os apps que você usa (depois ligue a chave Apps conectados do bot em Configurações → Acesso); sem eles o relatório avisa o que não conseguiu ver.
- **Tela do bot** (opcional): guardar o quadro de status e as receitas do que já foi resolvido.
  Como: ligue a Tela do bot; sem ela o histórico fica só na conversa.

## Habilidades incluídas

Elas chegam **desligadas**. Revise e ligue cada uma no perfil do bot.

- `delegacao-e-acompanhamento-de-pedidos`: Distribuir cada pedido ao bot certo do time com o briefing inteiro (coordinate_bots), acompanhar prazo, status e pendência, retomar quando alguém trava e levar à pessoa só o que depende dela. Use quando chegar um pedido…
- `relatorio-diario-da-operacao`: Montar o relatório da manhã da operação: o que precisa da pessoa, o que vence, as pendências de cada peça (capa, legenda, editor, data), os bots parados e o que está agendado. Use quando pedirem 'bom dia', 'como está a…
- `coordenacao-recorrente-entre-bots`: Montar automações que se repetem e envolvem mais de um bot: buscar um conteúdo em horário fixo, mandar ao bot que processa com a especificação completa, entregar o resultado e avisar a pessoa, mais lembretes repetidos a…
- `escolha-de-modelo-por-bot`: Escolher e aplicar o modelo de IA que cada bot do time usa: mapear o time, responder com uma tabela de bot por modelo com o nome exato do catálogo e a razão em uma frase, propor a troca pelas ferramentas do app e testar…
- `cancelamento-de-assinatura-na-web`: Cancelar ou rebaixar uma assinatura de serviço na web a partir de uma cobrança que a pessoa mostra: identificar o serviço e a conta, entrar pelo cartão de login sem a senha passar pelo chat, ler o estado antes, cancelar…
- `recuperacao-de-dominio-suspenso`: Descobrir por que um domínio parou de funcionar e restaurá-lo no registrador: ler o estado do registro antes de mexer, descartar falta de pagamento, reenviar a verificação do e-mail de contato, pedir à pessoa que clique…
- `consulta-de-fato-no-arquivo-de-email`: Responder perguntas de fato sobre o passado de uma conta (data de cadastro, compra, cobrança, confirmação) a partir do arquivo de e-mail da pessoa, citando a mensagem de origem com a data convertida para o fuso dela. Us…

## Como instalar

1. Abra **Modelos**, na barra lateral do Nordus, escolha este modelo e carregue. Ou importe o arquivo `gerente-de-operacao.nordusteam.json`. Você vê uma prévia antes de qualquer coisa ser adicionada.
2. Ligue as habilidades de cada bot.
3. Siga o **Antes de usar** acima.
4. Depois de conectar um app em **Apps conectados**, ligue a chave **Apps conectados** do bot em **Configurações → Acesso**. Sem isso o bot não enxerga o app.
5. Rotinas não vêm incluídas. Peça ao bot as automações de que você precisa.

## Autoria e licença

Autor: Nordus. Licença: Apache-2.0.
