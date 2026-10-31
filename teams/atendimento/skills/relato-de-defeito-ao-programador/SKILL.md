---
name: relato-de-defeito-ao-programador
description: "Montar e mandar ao programador do time o pacote de um defeito da plataforma (hora, ids, pedido visível, provedor, resposta do provedor e um patch pequeno) sem dados do cliente, esperar o aviso de correção no ar e só então responder ao cliente. Use quando um erro parecer defeito da plataforma e não bloqueio de conteúdo ou direito autoral do provedor."
---

# Relato de defeito ao programador

Quando o erro parece defeito da plataforma, o atendimento junta as evidências e propõe um patch; o programador confere, corrige e publica. O atendimento fala com o cliente; o programador não.

## Quando usar

- A triagem concluiu que o erro parece defeito da plataforma (veja `triagem-de-problema-e-reembolso`).
- Vários clientes batem no mesmo erro.

## Procedimento

1. **Devolva o crédito do cliente na hora** (conforme a política) e não responda ao cliente ainda.
2. **Abra a operação e junte o máximo que ela trouxer:**
   - hora (criação, início, fim e tentativas);
   - ids (da operação, do despacho e do pedido);
   - o pedido visível (modelo, modo, proporção, duração, origem);
   - o provedor ou motor;
   - a resposta do provedor (erro da operação, erro do despacho e código HTTP).
   A resposta crua do provedor chega cortada: não invente o que não veio.
3. **Ache a causa no código,** se tiver acesso ao código do produto: atualize a pasta do projeto para a versão que está em produção antes de ler e monte um patch pequeno. Sem acesso ao código, mande só as evidências.
4. **Mande ao programador** com `coordinate_bots`, em conversa nova, o pacote e o patch. **Sem e-mail do cliente e sem o texto da conversa.** Não publique você.
5. **Espere o aviso do programador** de que os testes passaram e a correção está no ar. Só então responda ao cliente: deu erro, o crédito voltou e já foi corrigido.
6. **Se o programador disser que não era defeito da plataforma,** explique o provedor ao cliente e pare.
7. **Avise a pessoa** só se houve correção de código: uma ou duas frases, com o número do atendimento e sem dado do cliente.

## Cuidados

- **Nunca mande dado pessoal do cliente** ao programador: o erro se explica pelos ids e pelas respostas do sistema.
- **Não prometa prazo de correção ao cliente.**
- **Um defeito, um pacote.** Se outro cliente bater no mesmo erro, acrescente os ids à conversa aberta em vez de abrir outra.
- **Sem programador no workspace,** entregue o pacote e o patch à pessoa e diga que o modelo PROGRAMADOR, em Modelos, na barra lateral, resolve esse caminho.

## Antes de dar por terminado

O pacote tem hora, ids, pedido visível, provedor e resposta do provedor, não carrega dado do cliente, o programador confirmou a correção e o cliente recebeu a resposta depois disso.
