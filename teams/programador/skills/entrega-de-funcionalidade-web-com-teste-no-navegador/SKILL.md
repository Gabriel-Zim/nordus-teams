---
name: entrega-de-funcionalidade-web-com-teste-no-navegador
description: "Construir e publicar uma funcionalidade web com teste automatizado no navegador e conferência em mais de um ambiente: estudar o código, desenvolver, escrever um roteiro de teste com capturas de tela, validar em staging, publicar em produção, conferir de novo e limpar os arquivos e credenciais temporários. Use quando pedirem uma funcionalidade nova ou uma correção que precisa de teste visual antes de ir ao ar."
---

# Entrega de funcionalidade web com teste no navegador

Fluxo completo para construir e publicar uma funcionalidade em uma aplicação web: desenvolvimento local, teste automatizado no navegador com capturas de tela, conferência em staging, publicação em produção e limpeza do que foi criado só para testar.

## Quando usar

- Construir uma funcionalidade nova (um sino de notificações, um painel de ajustes, um endpoint novo).
- Corrigir um erro ou mudar uma funcionalidade existente.
- Qualquer mudança que precisa de teste antes de ir ao ar, com código de servidor e de interface (JavaScript e CSS).

## Procedimento

1. **Estude o código antes.** Leia os arquivos relevantes para entender a estrutura, os padrões e onde a mudança entra. Mapeie os arquivos antes de escrever.
2. **Desenvolva e teste localmente**, seguindo os nomes e o estilo do projeto.
3. **Monte um roteiro de teste no navegador** com Playwright:
   - Use `--no-sandbox` para rodar sem tela.
   - Faça um script genérico que receba: usuário ou sessão, URL, caminho de saída, condições de espera e um trecho de JavaScript para avaliar.
   - Exemplo: `node captura.mjs <usuario> '<endereço da página>' /tmp/verificacao.png 'espera:3000' 'return !!document.querySelector(".sino")'`.
   - As capturas conferem a interface e as mudanças de estado sem clique manual.
4. **Guarde credenciais de teste com cuidado.**
   - Use tokens de sessão temporários do servidor, não senhas.
   - Guarde em arquivos com `chmod 600` ou passe por variável de ambiente.
   - Nunca grave senha em arquivo nem no controle de versão.
5. **Publique primeiro em staging:** copie o código, reinicie o serviço, espere estabilizar e rode o roteiro completo com dados reais.
6. **Confira em staging:** capture todos os caminhos do usuário (vazio, normal, erro), teste cada papel se a funcionalidade depende de papel, e confirme que nada regrediu. Só siga para produção se tudo passar.
7. **Publique em produção** (com o ok da pessoa na conversa): copie o código, reinicie do mesmo jeito e espere o serviço ficar saudável.
8. **Confira em produção na hora:** rode o mesmo roteiro com dados reais, tire as capturas finais e teste com mais de uma conta para confirmar visibilidade e controle de acesso.
9. **Limpe os artefatos de teste:** apague os arquivos de token (use `shred -u` nos sensíveis), as contas e os tokens de teste do servidor e os backups e scripts que sobraram em `/tmp` e nas pastas de trabalho. Peça o ok da pessoa antes de uma limpeza destrutiva.

## Cuidados

- **Publicar sem ler o código** quebra integrações e estilo: mapeie antes.
- **Pular o staging** deixa o erro visível ao usuário: sempre teste lá primeiro, com o mesmo roteiro.
- **Credenciais de teste esquecidas em produção** são confusão e risco: confirme que a limpeza terminou.
- **Sem conferência visual** o código passa e o CSS quebra: capturas pegam o que a leitura do código não pega.
- **Serviço sem reiniciar:** servidores guardam arquivos estáticos e módulos em memória, e só copiar não basta.
- **Staging não é produção:** configurações de ambiente (endereços, flags, esquemas) diferem, e algo que funciona em staging pode falhar no ar.
- **Arquivos temporários acumulados** em `/tmp` entopem: apague-os mesmo sendo "só temporários".
- **Capturas sem mídia:** imagens, vídeos e miniaturas podem carregar depois da página. Aumente a espera em passos de 2 a 3 segundos e repita; 7 a 10 segundos são normais em telas com muita mídia.

## Antes de dar por terminado

As capturas em staging mostram a funcionalidade sem defeito visual, as de produção batem com as de staging, a funcionalidade está visível para os usuários certos e não resta token, arquivo temporário ou conta de teste no servidor nem em `/tmp`.
