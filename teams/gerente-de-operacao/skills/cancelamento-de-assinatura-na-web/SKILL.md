---
name: cancelamento-de-assinatura-na-web
description: "Cancelar ou rebaixar uma assinatura de serviço na web a partir de uma cobrança que a pessoa mostra: identificar o serviço e a conta, entrar pelo cartão de login sem a senha passar pelo chat, ler o estado antes, cancelar sem aceitar pausa ou desconto e conferir o estado final. Use quando disserem 'cancela isso', 'não quero mais pagar X' ou mandarem o print de uma cobrança."
---

# Cancelamento de assinatura na web

Cancela ou rebaixa a assinatura de um serviço quando a pessoa mostra uma cobrança ou pede para parar uma renovação. Nunca inventa nem guarda credenciais.

## Quando usar

- A pessoa manda o print de uma cobrança ou fatura e diz "cancela isso", "dá um jeito de cancelar", "conta: <e-mail>".
- "Cancelar a assinatura", "precisa cancelar até amanhã para não renovar", "não quero mais pagar X".

## Procedimento

1. **Identifique o serviço e a conta** pela cobrança ou pelo e-mail da fatura (nome do comerciante, e-mail da conta). Diga em voz alta qual serviço e qual conta você vai cancelar, antes de agir.
2. **Abra o site do serviço** no navegador do bot e vá até a página de cobrança ou assinatura.
3. **Entre com `request_sign_in`.** O cartão serve para login direto e para "Continuar com Google": o que a pessoa digita vai para a página, não para o chat.
4. **Se a janela de login não abrir**, a conexão entre o app e o computador da pessoa pode estar desligada: peça que reconecte e tente o cartão de novo. Falha na janela do Google é problema de conexão, não prova de que o site é inacessível.
5. **Leia o estado atual primeiro**: plano, data de renovação, próxima cobrança. Anote antes de mudar qualquer coisa.
6. **Cancele, não pause.** Os fluxos de retenção empurram "pausar" e ofertas de desconto. Siga o caminho de cancelar e confirme cada tela de confirmação até a página mostrar cancelado ou rebaixado. A página costuma trocar o botão de cancelar por "pausar" ou por uma oferta depois do primeiro clique: releia a tela a cada passo.
7. **Confira o texto do estado final**: plano ativo até a data X, depois gratuito ou cancelado, sem cobrança de renovação agendada.
8. **Relate**: o que foi cancelado, de qual conta, até quando o acesso continua, e que uma cobrança já lançada não é estornada pelo cancelamento (o botão de suporte na área de cobrança é o caminho para pedir reembolso).
9. **Sem como entrar** (sem credenciais, login por SSO quebrado): prepare o pedido de cancelamento como rascunho de e-mail na conta conectada e peça o ok antes de enviar. Nunca envie por conta própria.

## Cuidados

- **Não diga que resolveu antes de ler a página de cobrança.** Quando a pessoa pergunta "conseguiu?" ou diz que cancelou, isso é um pedido para verificar, não um fato. Diga só o que a página mostra.
- **"Eu já cancelei" não é prova.** Abra a página e confirme: fluxo pausado ou pela metade deixa a renovação agendada. Plano ativo com data de renovação quer dizer que não foi cancelado.
- **Pausar não é cancelar.** Recuse pausa e desconto: eles mantêm a renovação viva e parecem uma solução.
- **Cancelar não devolve a cobrança já feita.** Avise que o estorno depende do suporte do serviço.
- **Login só com Google continua possível.** Não recorra ao e-mail de suporte enquanto o cartão de login puder levar o fluxo do Google; janela que falha costuma ser conexão desligada.
- **Rascunho não é enviado.** O e-mail ao suporte fica como rascunho até a pessoa aprovar; se ela resolveu de outro jeito, confirme que nada foi enviado e descarte o rascunho.

## Antes de dar por terminado

A página de cobrança mostra o plano cancelado ou com data de rebaixamento, sem renovação agendada, e a pessoa recebeu um resumo com o serviço, a conta, a data final do acesso e o aviso sobre reembolso.
