# TRÁFEGO PAGO

Time de nove bots que abre o projeto, testa criativos, opera a conta da Meta dentro de um teto e reporta o retorno, com revisão de política antes do ar.

## O que ele faz

Uma agência de tráfego pago feita de bots, para qualquer produto ou negócio, começando pela Meta. O gestor de tráfego fala com você e comanda um pesquisador de growth, um estrategista de mídia, um copywriter, um diretor de criativo, um revisor de políticas, um analista de resultado, um financeiro de mídia e um operador de campanhas. O time abre cada projeto com a conta da régua (retorno no caixa, não só o número da Meta), testa conceitos de criativo, publica só o que o revisor passou, corta e escala por regras com número, nunca passa do teto que você aprovou e entrega dois relatórios por dia em linguagem simples.

## O que você recebe

- Cada projeto aberto com meta de retorno, teto diário e mensal e freio do dia, aprovados por você uma vez.
- Anúncios testados por conceito, revisados contra a política da Meta e a lei brasileira antes de ir ao ar.
- Relatórios da manhã e do fim do dia com gasto, vendas e retorno no caixa, sem sigla e sem número inventado.

## Quem está no time

| Bot | Título | O que faz |
|---|---|---|
| GESTOR DE TRÁFEGO (líder) | Líder do time de tráfego | Única voz do time com você: abre o projeto, distribui, aprova as ordens, cobra e manda os relatórios da manhã e do fim do dia. |
| OPERADOR DE CAMPANHAS | Operador de campanhas | Único que escreve na conta da Meta: executa as ordens do gestor exatamente como vieram, confere as travas e devolve o resultado. |
| FINANCEIRO DE MÍDIA | Financeiro de mídia | Faz a conta de cada projeto, define o custo por venda alvo e o envelope do dia e do mês, avisa em 80% do teto e fecha o mês. |
| ANALISTA DE RESULTADO | Analista de resultado | Lê a conta e as vendas reais, calcula custo por venda, retorno no caixa e fadiga, classifica cada anúncio e faz a auditoria da semana. |
| REVISOR DE POLÍTICAS | Revisor de políticas de anúncio | Portão antes do ar: confere cada peça contra a política da Meta, a lei brasileira e a página de destino e dá PASSA, AVISA ou BLOQUEIA com motivo. |
| DIRETOR DE CRIATIVO | Diretor de criativo | Transforma hipótese e copy em briefing, pede a peça ao editor de vídeo ou ao designer, guarda a mídia com o hash e mantém o banco de criativos. |
| COPYWRITER | Copywriter | Escreve texto principal, título, descrição e roteiro curto por ângulo, só com alegações que têm prova e sem cara de IA. |
| ESTRATEGISTA DE MÍDIA | Estrategista de mídia | Monta a estrutura das campanhas, escolhe os testes da semana, aplica corte e escala com os números do analista e escreve as ordens. |
| PESQUISADOR DE GROWTH | Pesquisador de growth | Busca ideias de copy, criativo e tráfego fora e dentro de casa e entrega cartões de hipótese com link, força da prova e critério de corte. |

O bot marcado como líder entra como **Boss** da seção nova: é quem fala com você e coordena os outros bots do modelo. Os demais entram como bots comuns.

## Sala de grupo e instruções do time

O modelo traz a sala **Time de tráfego**, com o quadro de avisos e as instruções compartilhadas do time (papéis, regras de dinheiro e formato dos recados). Quem responde por padrão é o líder.

## Antes de usar

Tempo para configurar: cerca de 30 minutos.

- **Meta Ads** (obrigatório): ler resultados e operar a conta de anúncios.
  Como: em Apps conectados, ligue o conector de Meta Ads e entre com a conta que administra os anúncios (depois ligue a chave Apps conectados do bot em Configurações → Acesso).
- **Tela do bot** (obrigatória): guardar a ficha de cada projeto em arquivos (o time cria a pasta projetos sozinho).
  Como: ligue a Tela do bot em cada bot do time.
- **Vendas reais** (opcional): medir o retorno no caixa (gateway de pagamento ou plataforma de vendas, ou um relatório de vendas que você envia).
  Como: conecte a plataforma de vendas em Apps conectados ou envie o relatório de vendas ao gestor; sem isso o time lê só o que a Meta atribui.
- **Editor de vídeo e Designer gráfico** (opcional): produzir as peças de vídeo e de imagem dos anúncios.
  Como: adicione ao seu workspace os modelos EDITOR DE VÍDEO e DESIGNER GRÁFICO, que estão em Modelos, na barra lateral; o diretor de criativo pede as peças a eles.

## Habilidades incluídas

Elas chegam **desligadas**. Revise e ligue cada uma no perfil do bot.

- `gestao-do-time-de-trafego`: Procedimento do gestor de tráfego, líder do time de tráfego pago: abrir projeto (ficha com o financeiro e mensagem única à pessoa com oferta, meta, tetos e o pedido de confirmação), distribuir o trabalho ao time por coo…
- `execucao-de-ordens-de-campanha`: Procedimento do operador de campanhas: receber do gestor um lote de ordens em JSON, conferir o formato e as travas de execução (conta ativa, moeda e fuso, envelope, ritmo, revisão PASSA), executar cada ordem pela ferram…
- `economia-e-teto-de-midia`: Procedimento do financeiro de mídia: abrir a ficha de projeto novo, fazer a conta da régua (ticket médio com bumps e upsell, taxas, fator de impostos da Meta, CPA de empate e alvo no caixa e no Gerenciador), preparar o…
- `leitura-de-resultado-de-anuncios`: Procedimento do analista de resultado: conferir a conexão antes de qualquer número, ler os resultados da Meta por anúncio, conjunto e campanha e as vendas reais, calcular no terminal custo por venda, retorno no caixa co…
- `revisao-de-politica-de-anuncios`: Procedimento do revisor de políticas: ler a peça montada pelo diretor de criativo (texto, título, descrição, link, botão e mídia), ver a mídia de verdade, conferir contra a política da Meta, a lei brasileira, as alegaçõ…
- `direcao-de-criativo-para-anuncios`: Procedimento do diretor de criativo: abrir a pasta do criativo no banco do projeto, separar conceito de variação pela crença, pedir a peça ao editor de vídeo ou ao designer gráfico do time por coordinate_bots (ou usar o…
- `copy-de-anuncios`: Procedimento do copywriter: para cada criativo pedido pelo gestor, montar o livro de alegações a partir da ficha do projeto, escolher a estrutura de texto que a prova sustenta, escrever texto principal, título, descriçã…
- `estrategia-e-ordens-de-midia`: Procedimento do estrategista de mídia: montar a estrutura das campanhas (uma campanha de vendas Advantage+ e um conjunto enquanto o orçamento diário for pequeno (abaixo de sete vezes o CPA alvo, ou seja, menos de cerca…
- `pesquisa-de-growth-para-anuncios`: Procedimento do pesquisador de growth: com o contexto de um projeto que o gestor manda, pesquisar estratégias de copy, criativo e tráfego em redes sociais, na Biblioteca de Anúncios da Meta, no YouTube, em comunidades e…

## Como instalar

1. Abra **Modelos**, na barra lateral do Nordus, escolha este modelo e carregue. Ou importe o arquivo `trafego-pago.nordusteam.json`. Você vê uma prévia antes de qualquer coisa ser adicionada.
2. Ligue as habilidades de cada bot.
3. Siga o **Antes de usar** acima.
4. Depois de conectar um app em **Apps conectados**, ligue a chave **Apps conectados** do bot em **Configurações → Acesso**. Sem isso o bot não enxerga o app.
5. Rotinas não vêm incluídas. Peça ao bot as automações de que você precisa.

## Autoria e licença

Autor: Nordus. Licença: Apache-2.0.
