# ATENDIMENTO

Atendimento ao cliente que responde o chat e o e-mail de suporte do seu produto, trata falhas e cuida do pós-venda, dentro de uma política que você aprova.

## O que ele faz

Um atendimento que responde sozinho, dentro de uma política de atendimento que você escreve e aprova com ele, a quem escreve no chat do site e no e-mail de suporte: relê a conversa, responde uma vez, ignora spam e resposta automática, confirma falhas no registro do serviço e devolve crédito só do que falhou. Defeito da plataforma vai ao programador com as evidências, sem dado do cliente. Reembolso em dinheiro, cancelamento e exceção ficam com você. Também cuida do pós-venda (boas-vindas, satisfação, risco de cancelamento e relatório dos problemas que mais se repetem), sempre com o seu ok para o que ele inicia.

## O que você recebe

- Clientes respondidos no chat e no e-mail, uma resposta por mensagem, no tom e dentro da política que você aprovou.
- Falhas conferidas no erro real, crédito devolvido só quando cabe e defeitos da plataforma encaminhados ao programador com as evidências.
- Pós-venda com mensagens aprovadas por você e um relatório semanal dos problemas que mais se repetem.

## Quem está no time

| Bot | Título | O que faz |
|---|---|---|
| ATENDIMENTO | Atendimento ao cliente | Responde o chat e o e-mail de suporte do seu produto dentro de uma política aprovada por você, trata falhas e cuida do pós-venda. |

## Antes de usar

Tempo para configurar: cerca de 20 minutos.

- **Caixa de e-mail de suporte** (obrigatória): ler e responder os e-mails dos clientes.
  Como: em Apps conectados, ligue o app do seu e-mail e entre com a conta do suporte (depois ligue a chave Apps conectados do bot em Configurações → Acesso); sem ele o atendimento não consegue atender por e-mail.
- **Chat do site** (opcional): responder as conversas do chat do seu site.
  Como: em Apps conectados, aba Conexões avançadas, ligue o servidor do seu chat ou sistema de atendimento, com o endereço e a chave que ele informa; sem ele o atendimento fala só por e-mail.
- **Sistema do seu produto** (opcional): consultar operações dos clientes e devolver crédito de operações que falharam.
  Como: em Apps conectados, aba Conexões avançadas, ligue o servidor MCP do seu produto (endereço e chave pelo seu painel de desenvolvedor); sem ele os casos de estorno vão para você.
- **Programador** (opcional): corrigir os defeitos da plataforma que os clientes relatam.
  Como: adicione ao mesmo workspace o modelo PROGRAMADOR, que está em Modelos, na barra lateral; sem ele o atendimento entrega as evidências e o patch a você.
- **Tela do bot** (opcional): guardar a política de atendimento, as respostas padrão e o registro.
  Como: ligue a Tela do bot; sem ela a política fica só na conversa.

## Habilidades incluídas

Elas chegam **desligadas**. Revise e ligue cada uma no perfil do bot.

- `atendimento-por-chat-e-email`: Atender clientes no chat do site e no e-mail de suporte: reler a conversa antes de responder, responder só quando a última mensagem é do cliente, mandar uma resposta só para várias mensagens seguidas, ignorar newsletter…
- `triagem-de-problema-e-reembolso`: Tratar o cliente que diz que o serviço não chegou ou deu falha: achar a operação no registro, confirmar a falha no erro real, devolver o crédito só do que falhou e não foi entregue (conforme a política), explicar bloque…
- `relato-de-defeito-ao-programador`: Montar e mandar ao programador do time o pacote de um defeito da plataforma (hora, ids, pedido visível, provedor, resposta do provedor e um patch pequeno) sem dados do cliente, esperar o aviso de correção no ar e só ent…
- `pos-venda-e-satisfacao`: Cuidar do pós-venda de um produto digital: mensagem de boas-vindas e primeira semana, acompanhamento depois de alguns dias, pesquisa curta de satisfação, tratamento de reclamação, sinal de risco de cancelamento e relató…
- `politica-de-atendimento`: Criar e manter a política de atendimento do produto (atendimento/politica.md): o que o atendimento resolve sozinho, a regra de crédito e reembolso, o que é decisão da pessoa, a voz, as respostas padrão e quem avisar. Us…

## Como instalar

1. Abra **Modelos**, na barra lateral do Nordus, escolha este modelo e carregue. Ou importe o arquivo `atendimento.nordusteam.json`. Você vê uma prévia antes de qualquer coisa ser adicionada.
2. Ligue as habilidades de cada bot.
3. Siga o **Antes de usar** acima.
4. Depois de conectar um app em **Apps conectados**, ligue a chave **Apps conectados** do bot em **Configurações → Acesso**. Sem isso o bot não enxerga o app.
5. Rotinas não vêm incluídas. Peça ao bot as automações de que você precisa.

## Autoria e licença

Autor: Nordus. Licença: Apache-2.0.
