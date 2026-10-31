---
name: recuperacao-de-dominio-suspenso
description: "Descobrir por que um domínio parou de funcionar e restaurá-lo no registrador: ler o estado do registro antes de mexer, descartar falta de pagamento, reenviar a verificação do e-mail de contato, pedir à pessoa que clique no link da mensagem e confirmar a volta. Use quando disserem 'o site caiu', 'domínio suspenso' ou quando um e-mail do registrador avisar suspensão."
---

# Recuperação de domínio suspenso

Diagnostica por que um domínio parou de resolver e o restaura no registrador. Cobre a leitura do registro e do painel, a verificação do e-mail de contato e a propagação. Não cobre erro de registro DNS, queda de hospedagem nem transferência de domínio.

## Quando usar

- "Meu domínio caiu", "o site saiu do ar", "domínio suspenso", ou um e-mail do registrador dizendo que o domínio está suspenso ou em espera.
- `whois` mostra `clientHold` ou `serverHold`, ou o site abre uma página de suspensão ou de estacionamento.

## Procedimento

1. **Leia o estado do registro antes de mexer em qualquer coisa**: `dig +short NS <domínio>`, `whois <domínio>` (ou o RDAP do registrador) e `curl -sI https://<domínio>`. Anote os códigos de estado e a data de expiração.
2. **Descarte falta de pagamento.** Expiração a meses de distância quer dizer que a suspensão não é falta de pagamento. Domínio registrado há pouco e parado costuma estar com o e-mail de contato sem verificar.
3. **Abra o painel do registrador** no navegador do bot e entre com `request_sign_in`.
4. **Abra a página do domínio e leia o aviso de suspensão**; ele nomeia o endereço de contato que falta verificar.
5. **Reenvie o e-mail de verificação** pelo painel e diga à pessoa exatamente qual caixa abrir, inclusive o spam.
6. **A pessoa precisa abrir a mensagem e clicar no link de verificação.** Entrar na caixa de e-mail não verifica nada. Peça a confirmação do clique, não do login.
7. **Force a atualização do estado**: depois da confirmação, use o controle de verificar ou atualizar do painel e consulte o registro de novo. O bloqueio costuma sair em minutos, às vezes em até meia hora.
8. **Confirme a recuperação**: o aviso do painel sumiu, o registro não mostra bloqueio e o site responde HTTP 200.

## Cuidados

- **Suspensão nem sempre é pagamento.** Olhe a data de expiração e a de registro antes: domínios novos ficam retidos por e-mail de contato sem verificação, mesmo pagos.
- **Entrar na caixa não faz nada.** Só o link dentro da mensagem libera o bloqueio; peça o clique de forma explícita.
- **Bloqueio logo depois do clique é esperado.** Cache do registro e propagação demoram: consulte de novo ao longo de minutos antes de concluir que o clique falhou.
- **Não deixe automação de verificação rodando sem aprovação.** Um vigia que consulta de tempos em tempos precisa da autorização da pessoa; sem ela, confira manualmente na conversa.
- **Painel e registro divergem por um tempo.** Quando o painel já não mostra suspensão, só falta a propagação do DNS: relate isso em vez de reiniciar o processo.

## Antes de dar por terminado

`whois` ou RDAP não lista mais `clientHold` nem `serverHold`, `curl -sI https://<domínio>` devolve 200 e o painel mostra o domínio ativo, sem aviso de verificação.
