---
name: mudanca-de-codigo-com-seguranca
description: "Alterar código com segurança do pedido ao ar: pegar a última versão e ler as instruções do repositório, trabalhar num ramo próprio, mudar só o necessário, rodar testes, checagem de tipos e lint, commitar com caminhos explícitos, juntar a versão remota sem descartar o trabalho dos outros, enviar sem force e publicar só com o ok. Use em qualquer pedido de corrigir, criar ou mudar um site, uma plataforma ou um app."
---

# Mudança de código com segurança

O caminho completo de uma mudança de código, do pedido até estar no ar, sem estragar a saúde do repositório.

## Quando usar

- "Corrige isso no site", "cria essa página", "muda esse comportamento", "publica a correção".
- Qualquer mudança em código, configuração ou conteúdo versionado de um projeto.

## Procedimento

1. **Pegue a última versão e leia antes de editar.** Busque o remoto (`git fetch origin`), crie o ramo de trabalho a partir da linha de integração do projeto (a principal ou a que o README indicar) e leia as instruções da raiz (AGENTS.md, CLAUDE.md, README, CONTRIBUTING) e o código e os testes da parte que vai mudar. Nunca trabalhe em cima de versão velha.
2. **Feche o que conta como pronto.** Se o pedido não diz, escreva em uma frase e confirme com a pessoa antes de começar.
3. **Mude só o necessário.** Sem refatoração de carona, sem arquivo fora do escopo.
4. **Verifique.** Rode os testes dos arquivos tocados, a checagem de tipos e o lint do projeto. Se o projeto não tem algum deles, diga isso na resposta.
5. **Commite com caminhos explícitos**, nunca com `git add -A`. Mensagem curta que diz o porquê.
6. **Junte a versão remota.** Com tudo verde: `git fetch origin` e `git merge origin/<linha>` no seu ramo. Se houver conflito, resolva sem descartar o trabalho de ninguém e teste de novo. Depois envie ao remoto (`git push origin HEAD:<linha>` ou abra o pedido de merge, conforme o projeto). **Nunca use force.** Push recusado: busque de novo, junte e repita.
7. **Publique só com o ok explícito da pessoa na conversa**, usando o comando de publicação do projeto. A última linha da saída precisa mostrar que a conferência passou. Se a conferência falhar, avise a pessoa na hora com o que falhou. Não tente voltar a versão por conta própria, a não ser que ela peça. Se o projeto reinicia serviços e há bots no meio de uma tarefa, espere terminar (até uns 20 minutos) e só use a opção de forçar com o ok da pessoa.
8. **Responda curto**: o que mudou e que já está no ar. Sem hash, sem comando, sem nome de arquivo, a não ser que perguntem.

## Cuidados

- **Segredos:** nunca mostre, copie, comite nem envie chave, token ou senha. Não crie nem comite `.env` real.
- **Pastas de outras sessões e projetos fora da tarefa:** não mexa.
- **Backup antes de apagar ou mudar** dados ou arquivos de produção. Diga à pessoa onde ficou.
- **Depois de reiniciar um serviço**, confira que está saudável e que a página responde. Se não, volte o backup, reinicie e avise.
- **Item de teste seu pode ser apagado;** dado de cliente real só com pedido explícito da pessoa.
- **Ferramentas de código podem responder em inglês.** Você resume em português do Brasil.

## Antes de dar por terminado

Testes, checagem de tipos e lint passaram (ou foi dito que o projeto não os tem), o commit tem só os caminhos da tarefa, a publicação foi autorizada e a conferência final passou, e a pessoa recebeu a resposta curta.
