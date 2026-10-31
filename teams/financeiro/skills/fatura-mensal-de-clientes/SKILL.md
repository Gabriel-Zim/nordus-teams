---
name: fatura-mensal-de-clientes
description: "Fechar as faturas mensais dos clientes: ler a tabela de clientes e contratos, calcular o que vence no mês, preparar cada fatura com período, descrição, valor, vencimento e forma de pagamento, mostrar o lote para o ok da pessoa, enviar só depois dele e registrar o que foi enviado. Use quando pedirem 'fecha as faturas do mês', 'manda a fatura do cliente X', 'quanto cada cliente deve este mês' ou na data de fechamento."
---

# Fatura mensal de clientes

Fecha o ciclo de cobrança do mês: o que cada cliente deve, a fatura pronta e o registro do envio. Nada sai sem o ok da pessoa.

## Quando usar

- "Fecha as faturas do mês", "manda a fatura do cliente X", "quanto cada cliente deve este mês".
- Na data de fechamento combinada (a pessoa pode pedir uma automação para lembrar).

## Procedimento

1. **Leia a tabela de clientes e contratos** (planilha conectada ou `financeiro/clientes.csv`): cliente, serviço, valor, dia de vencimento, forma de pagamento, e-mail de cobrança, observações. Se faltar a tabela, peça e pare.
2. **Calcule o que vence no mês** para cada cliente: valor fixo do contrato, mais extras que a pessoa listou, menos descontos acordados. Cada número tem origem na tabela, no contrato ou numa mensagem da pessoa. O que você não consegue rastrear fica de fora e vai para a pessoa como pergunta.
3. **Prepare a fatura** de cada cliente com: identificação de quem cobra e de quem paga, período de referência, descrição de cada item, valor de cada um e total, data de vencimento e forma de pagamento (link, boleto, Pix ou dados bancários informados pela pessoa). Gere o PDF ou o texto do e-mail, conforme o combinado.
4. **Mostre o lote à pessoa** numa tabela curta (cliente, total, vencimento) e destaque o que mudou em relação ao mês anterior e o que ficou de fora com o motivo. Peça o ok em texto.
5. **Envie só depois do ok**, cada fatura para o e-mail de cobrança do cliente, com texto curto e cordial. Não copie outros clientes e não anexe nada de outro cliente.
6. **Registre** no razão (`financeiro/razao.csv`): cliente, mês, valor, vencimento, data do envio, situação (enviada, paga, atrasada). Atualize a situação quando chegar o pagamento (veja `triagem-de-alertas-bancarios`).
7. **Relate à pessoa** quantas faturas saíram, o total faturado e o que ficou pendente de decisão.

## Cuidados

- **Não invente valor, desconto nem prazo.** Divergência entre tabela e contrato é pergunta, não escolha sua.
- **Reajuste, multa e juros** só entram se estiverem no contrato ou se a pessoa mandar; cite a cláusula ou a mensagem.
- **Fatura duplicada** confunde o cliente: confira no razão se o mês já foi enviado antes de enviar.
- **Cada fatura vai para um cliente só,** com os dados dele.
- **Dado de pagamento errado** gera pagamento perdido: confira a chave Pix, o boleto ou a conta com a pessoa na primeira fatura de cada cliente.

## Antes de dar por terminado

Todo valor tem origem rastreável, o lote foi aprovado pela pessoa antes do envio, o razão registra cada envio e nenhuma fatura saiu em duplicidade.
