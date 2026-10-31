---
name: consulta-de-fato-no-arquivo-de-email
description: "Responder perguntas de fato sobre o passado de uma conta (data de cadastro, compra, cobrança, confirmação) a partir do arquivo de e-mail da pessoa, citando a mensagem de origem com a data convertida para o fuso dela. Use quando perguntarem 'em que dia assinei X', 'quando comprei Y', 'desde quando pago Z' ou 'confere pelo e-mail'."
---

# Consulta de fato no arquivo de e-mail

Responde a perguntas de fato sobre ações passadas de uma conta (cadastros, compras, cobranças, confirmações) a partir do arquivo de e-mail da pessoa, e cita a mensagem. Não escreve nem envia e-mail e não resume a caixa de entrada atual.

## Quando usar

- "Em que dia assinei a hospedagem X?", "quando comprei Y?", "desde quando pago Z?", "me manda a confirmação de W".
- "Olha pelo e-mail", "procura no e-mail", "confere na caixa" ligado a uma pergunta de quando ou se algo aconteceu.

Precisa do app de e-mail conectado. Se não houver, diga que falta e como conectar (Apps conectados e a chave Apps conectados do bot em Configurações → Acesso) em vez de responder de memória.

## Procedimento

1. **Busque primeiro na caixa de e-mail conectada**, antes de qualquer resumo, diário ou cópia local. O arquivo guarda a data original e a pessoa trata a caixa como fonte da verdade.
2. **Busque pelo fornecedor e pelo meio de pagamento.** Pesquise o nome do fornecedor, depois o meio de pagamento (PayPal, emissor do cartão) junto com o endereço da conta. Cópias locais do e-mail só indicam onde olhar; toda data que você relatar vem de uma mensagem aberta na caixa.
3. **Abra as mensagens encontradas** e leia o cabeçalho Date, não o trecho de prévia.
4. **Relate a data e o evento**: conta criada, pagamento autorizado, serviço ativado, cada um com o horário exato convertido para o fuso da pessoa.
5. **Nomeie a fonte** (de qual remetente é a mensagem) para a resposta poder ser conferida.
6. **Se nada bater**, diga o que você buscou (fornecedor, meio de pagamento, endereço) antes de pedir outro dado.

## Cuidados

- **Cópia local ou resumo de sessão é derivado, não prova.** Pode estar incompleto ou ter desviado da caixa. Quando a pessoa diz "olha pelo e-mail", abra a mensagem original e cite o cabeçalho Date.
- **Datas do fornecedor e do meio de pagamento diferem.** Criação da conta, autorização do pagamento e ativação são horários distintos, em geral com minutos de diferença. Dê os três quando a pergunta for "quando assinei".
- **Cabeçalhos brutos vêm em UTC.** Converta antes de responder; horário sem conversão parece uma hora ou mais errado.
- **Não responda pelo site público do fornecedor.** Ele mostra o plano, não a data em que a pessoa criou a conta.

## Antes de dar por terminado

A resposta traz uma data e hora que batem com o cabeçalho Date de uma mensagem identificada, com o remetente nomeado.
