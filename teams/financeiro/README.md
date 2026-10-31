# FINANCEIRO

Assistente financeiro que fecha as faturas mensais dos clientes, acompanha os alertas do banco, cobra atrasos e responde dúvidas, sem mexer no seu dinheiro.

## O que ele faz

Um assistente financeiro que prepara as faturas mensais a partir da sua tabela de clientes e contratos, mostra o lote para o seu ok antes de enviar, lê os alertas do banco no e-mail e casa as entradas com as faturas abertas, cobra atrasos numa régua educada e responde às dúvidas de cobrança dos clientes. Não paga, não transfere e não clica em link de banco. Desconto, parcelamento, reembolso e cancelamento ficam com você. Dado financeiro não vai para outro bot nem para outro cliente.

## O que você recebe

- Faturas do mês prontas, com cada valor rastreado na tabela ou no contrato, aprovadas por você antes do envio.
- Entradas do banco casadas com as faturas abertas e um razão sempre atualizado.
- Cobranças educadas na hora certa e dúvidas de cliente respondidas sem prometer o que só você decide.

## Quem está no time

| Bot | Título | O que faz |
|---|---|---|
| FINANCEIRO | Assistente financeiro | Fecha as faturas mensais dos clientes, lê os alertas do banco, cobra atrasos e responde dúvidas, sem mexer no seu dinheiro. |

## Antes de usar

Tempo para configurar: cerca de 10 minutos.

- **E-mail** (obrigatório): ler os alertas do banco e enviar faturas e cobranças depois do seu ok.
  Como: em Apps conectados, ligue o app da sua caixa de e-mail e entre com a sua conta (depois ligue a chave Apps conectados do bot em Configurações → Acesso); sem ele o financeiro trabalha só com o que você colar na conversa.
- **Tabela de clientes e contratos** (obrigatória): saber o valor, o vencimento, a forma de pagamento e o e-mail de cobrança de cada cliente.
  Como: conecte a planilha que você usa em Apps conectados, ou ligue a Tela do bot e coloque o arquivo financeiro/clientes.csv; sem a tabela o bot não fecha fatura e não inventa valores.
- **Plataforma de cobrança** (opcional): gerar link de pagamento, boleto ou Pix nas faturas.
  Como: em Apps conectados, ligue o app de pagamentos que você usa (depois ligue a chave Apps conectados do bot em Configurações → Acesso); sem ele a fatura leva os dados de pagamento que você informar.
- **Tela do bot** (opcional): guardar as faturas em PDF e o razão de entradas e saídas.
  Como: ligue a Tela do bot; sem ela o registro fica na conversa.

## Habilidades incluídas

Elas chegam **desligadas**. Revise e ligue cada uma no perfil do bot.

- `fatura-mensal-de-clientes`: Fechar as faturas mensais dos clientes: ler a tabela de clientes e contratos, calcular o que vence no mês, preparar cada fatura com período, descrição, valor, vencimento e forma de pagamento, mostrar o lote para o ok da…
- `triagem-de-alertas-bancarios`: Ler os alertas do banco que chegam por e-mail, classificar (entrada, saída, cobrança, segurança, suspeito), casar entradas com faturas abertas, registrar no razão e avisar a pessoa do que importa, sem clicar em link, se…
- `cobranca-e-atendimento-financeiro`: Cobrar faturas em atraso com educação e objetividade e responder às dúvidas financeiras dos clientes: lembrete antes do vencimento, avisos depois dele com a situação real, o que é decisão da pessoa (desconto, parcelamen…

## Como instalar

1. Abra **Modelos**, na barra lateral do Nordus, escolha este modelo e carregue. Ou importe o arquivo `financeiro.nordusteam.json`. Você vê uma prévia antes de qualquer coisa ser adicionada.
2. Ligue as habilidades de cada bot.
3. Siga o **Antes de usar** acima.
4. Depois de conectar um app em **Apps conectados**, ligue a chave **Apps conectados** do bot em **Configurações → Acesso**. Sem isso o bot não enxerga o app.
5. Rotinas não vêm incluídas. Peça ao bot as automações de que você precisa.

## Autoria e licença

Autor: Nordus. Licença: Apache-2.0.
