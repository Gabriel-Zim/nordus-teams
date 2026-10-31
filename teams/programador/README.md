# PROGRAMADOR

Programador que altera, testa, commita e publica sites e plataformas, sempre pela última versão e só com o seu ok para ir ao ar.

## O que ele faz

Um programador que começa sempre pela última versão do projeto, lê as instruções do repositório, muda só o necessário, roda testes, checagem de tipos e lint, commita com caminhos explícitos, junta a versão remota sem descartar o trabalho de ninguém e nunca usa force. Testa funcionalidades web no navegador com capturas de tela em staging e em produção, trata relatos de erro vindos do atendimento (confere o patch, roda os testes e avisa em uma frase) e só publica com o seu ok na conversa. Nunca mostra chave, token ou senha.

## O que você recebe

- Mudanças de código pequenas e verificadas, com testes, tipos e lint rodados antes de ir ao ar.
- Funcionalidades web conferidas no navegador, com capturas, em staging e depois em produção.
- Erros relatados pelo atendimento conferidos contra o patch e corrigidos, com uma frase de volta a quem relatou.

## Quem está no time

| Bot | Título | O que faz |
|---|---|---|
| PROGRAMADOR | Programador | Altera, testa, commita e publica sites e plataformas pela última versão do projeto, e só vai ao ar com o seu ok. |

## Antes de usar

Tempo para configurar: cerca de 15 minutos.

- **Tela do bot** (obrigatória): guardar o código, rodar o terminal, os testes e o git.
  Como: ligue a Tela do bot e dê acesso à pasta do projeto; sem ela o programador explica o que falta e não finge ter rodado nada.
- **Repositório de código (git)** (obrigatório): buscar a última versão e enviar as mudanças.
  Como: deixe o git do computador autenticado no repositório do projeto (por exemplo, com a CLI do GitHub); o bot pede o login pelo cartão de entrada, sem a senha passar pelo chat.
- **Hospedagem** (opcional): publicar o site ou a plataforma.
  Como: entre na CLI da hospedagem que você usa (por exemplo, a do Cloudflare) no computador do bot; sem isso o bot deixa a mudança pronta e pede a publicação a você.
- **GitHub** (opcional): abrir pedidos de merge e ler issues.
  Como: em Apps conectados, ligue o app do GitHub e entre com a sua conta (depois ligue a chave Apps conectados do bot em Configurações → Acesso).
- **Atendimento** (opcional): receber relatos de erro de clientes com as evidências e um patch.
  Como: adicione ao mesmo workspace o modelo ATENDIMENTO, que está em Modelos, na barra lateral.

## Habilidades incluídas

Elas chegam **desligadas**. Revise e ligue cada uma no perfil do bot.

- `mudanca-de-codigo-com-seguranca`: Alterar código com segurança do pedido ao ar: pegar a última versão e ler as instruções do repositório, trabalhar num ramo próprio, mudar só o necessário, rodar testes, checagem de tipos e lint, commitar com caminhos ex…
- `entrega-de-funcionalidade-web-com-teste-no-navegador`: Construir e publicar uma funcionalidade web com teste automatizado no navegador e conferência em mais de um ambiente: estudar o código, desenvolver, escrever um roteiro de teste com capturas de tela, validar em staging,…
- `correcao-a-partir-de-relato-de-erro`: Tratar um relato de erro vindo do atendimento (hora, ids, pedido, provedor, resposta do provedor e um patch): conferir se o patch explica o erro, aplicar, rodar só os testes do que mudou, publicar a correção quando a pe…

## Como instalar

1. Abra **Modelos**, na barra lateral do Nordus, escolha este modelo e carregue. Ou importe o arquivo `programador.nordusteam.json`. Você vê uma prévia antes de qualquer coisa ser adicionada.
2. Ligue as habilidades de cada bot.
3. Siga o **Antes de usar** acima.
4. Depois de conectar um app em **Apps conectados**, ligue a chave **Apps conectados** do bot em **Configurações → Acesso**. Sem isso o bot não enxerga o app.
5. Rotinas não vêm incluídas. Peça ao bot as automações de que você precisa.

## Autoria e licença

Autor: Nordus. Licença: Apache-2.0.
