---
name: leitura-de-resultado-de-anuncios
description: "Procedimento do analista de resultado: conferir a conexão antes de qualquer número, ler os resultados da Meta por anúncio, conjunto e campanha e as vendas reais, calcular no terminal custo por venda, retorno no caixa com o fator de impostos, taxa de gancho, retenção, fadiga e saúde da medição, classificar cada anúncio (dados insuficientes, cortar, fadiga, observar, manter, escalar), dar os números dos relatórios do gestor e fazer a auditoria da semana. Use em todo pedido do gestor de leitura, números do relatório, auditoria ou medição."
---

# Analista de resultado: números que o caixa confirma

Regras de sempre (ver sua alma): só o gestor, nunca inventar número, conexão antes de número, o caixa decide, você só lê e recomenda, um projeto por vez, conta no terminal, sem segredo, sem travessão.

Suas ferramentas são as de leitura da Meta (estado da conta, estrutura, resultados, alertas), a fonte de vendas reais do projeto e a Tela do bot. Dinheiro vem da ferramenta em centavos; converta para reais só no texto.

## 0. Raízes e leitura

```sh
QG=$(cd -P projetos/.. && pwd)
F="$QG/projetos/<projeto>"
mkdir -p "$F/analises"
```

Do projeto, leia `$F/economia.md` (CPA alvo e de empate, fator de impostos) e as leituras anteriores em `$F/analises/`. Ao começar cada parte, `informar_etapa` com uma linha no gerúndio e o projeto.

## 1. Conexão primeiro

Toda rodada começa pelo estado da conta do projeto.
- Falhou: pare. Recado com "não consegui ler a conta" e o erro, sem nenhum número.
- Conta fora de ativa: diga na primeira linha do FEITO, com o motivo que voltou.
- Tabela vazia de resultados só é "sem entrega" depois que o estado da conta voltou certo nesta rodada.

## 2. O que chega do gestor

| Mensagem | Seção |
|---|---|
| "<Projeto> · Leitura" | 3 |
| "<Projeto> · Números do relatório da manhã" ou "da tarde" | 4 |
| "<Projeto> · Auditoria da semana" | 5 |
| "<Projeto> · Medição" | 6 |

Pedido de outro bot ou de uma pessoa: diga que os pedidos do time passam pelo gestor.

## 3. Leitura do dia

1. Puxe os resultados de ontem e dos últimos 7 dias nos níveis anúncio, conjunto e campanha; as vendas reais de ontem, 7 dias e mês até hoje; a estrutura (situação de cada objeto e aprendizado); o `livro.md` do projeto (o que mudou desde a última leitura); os alertas.
2. Salve as respostas cruas em `$F/analises/<AAAAMMDD>-dados.json` e faça as contas com um script no terminal que lê esse arquivo, nunca de cabeça:
   - CPA = gasto ÷ compras (totais; nunca média de médias);
   - taxa de gancho = visualizações de 3 s ÷ impressões; retenção = ThruPlay ÷ visualizações de 3 s;
   - CTR de link e frequência, como vieram;
   - pico do CTR de cada anúncio = o maior CTR de link diário nas leituras anteriores; sem histórico, consulte os resultados dia a dia desde a criação;
   - gasto no caixa = gasto × fator de impostos; retorno no caixa = receita bruta ÷ gasto no caixa.
3. Classifique cada anúncio, na ordem, pelas regras abaixo, com os dois sinais quando houver. Diga quando o anúncio de "dados insuficientes" vai dar para julgar.
4. Responda cinco perguntas, uma linha cada: o gasto está no ritmo do teto? o que está rodando de verdade? como foram os últimos 7 dias contra a meta? quem ganha e quem perde? há fadiga?
5. Medição: compras da Meta contra vendas reais, ontem e 7 dias (seção 6).
6. Escreva `$F/analises/<AAAAMMDD>-leitura.md` com uma tabela por anúncio (id, gasto, impressões, CTR de link, taxa de gancho, retenção, frequência, compras, CPA, classificação) e as respostas. Cada tabela leva a janela e a fonte.

### Regras de classificação

- **Dados insuficientes:** menos de 48 horas no ar, ou menos de 1 CPA alvo de gasto, ou menos de 3 vendas. Nada se julga por um dia ruim; decida por gasto acumulado.
- **Cortar** (pausar pede dois sinais juntos; um sinal só vira "observar"): até 2.000 impressões com taxa de gancho abaixo de 22%; 1 CPA alvo de gasto com CTR de link abaixo de 0,8% e taxa de gancho abaixo de 25%; 2 a 3 CPAs alvo de gasto sem venda; 3 CPAs alvo de gasto com CPA acima do de empate.
- **Fadiga:** CTR de link 20% abaixo do pico do anúncio e frequência acima de 3. Frequência acima de 3,5 é aviso antes do CTR cair. Queda de 1 a 2 dias com frequência abaixo de 2,5: esperar.
- **Escalar:** CPA de 7 dias abaixo do alvo, conjunto fora da fase de aprendizado, campanha que não está caindo.
- **Manter:** dentro do alvo, sem sinal de corte ou de fadiga. **Observar:** um sinal só.
- O CPA de um anúncio sozinho engana: a Meta gasta mais num anúncio caro para baratear os outros. Antes de cortar o que mais gasta, olhe o CPA do conjunto.

## 4. Números do relatório

Devolva, no FEITO, este bloco, com a janela de cada linha:

```
NUMEROS <Projeto> · <janela>
gasto no Gerenciador: R$ <x>
gasto no caixa: R$ <x> (x fator de impostos)
entrou: R$ <receita bruta> em <n> vendas
retorno no caixa: <x>
mês até hoje: gasto no caixa R$ <x>, entrou R$ <x>, retorno <x>
teto mensal: R$ <x> no Gerenciador, R$ <x> no caixa
compras que a Meta viu: <n>
não consegui ler: <o quê, ou "nada">
```

Manhã: janela "ontem". Tarde: janela "hoje até agora". O gestor confere seus totais contra as ferramentas antes de mandar.

## 5. Auditoria da semana

Às quintas, escreva `$F/analises/<AAAAMMDD>-auditoria.md` com:
1. Estrutura: campanhas, conjuntos e anúncios, situação de cada um, orçamento, se algum está em aprendizado limitado (para sair da fase, um conjunto precisa de cerca de 50 compras em 7 dias).
2. Entrega: anúncio reprovado, com erro ou sem entrega, e o motivo que a Meta deu.
3. Criativos: o que está no ar contra o banco (`$F/criativos/*/criativo.md`), conceitos diferentes no ar, quantos dias cada um tem, quem está perto da fadiga.
4. Resultado da semana: gasto, vendas reais, retorno no caixa, CPA contra alvo e empate.
5. Ritmo do mês: gasto até hoje mais o teto diário vezes os dias que faltam, contra o teto mensal.
6. Medição da semana (seção 6).
7. Lições: o que venceu e perdeu, em linhas que levam a dado desta auditoria.
8. Recomendações, 2 a 4, cada uma com o dado que a motiva e quem executa: estrategista (ordem), diretor de criativo (criativo novo), gestor (algo da pessoa). Escreva como teste, não como certeza.

## 6. Medição

- O site manda a compra por dois caminhos, o Pixel no navegador e a API de Conversões no servidor, com o mesmo `event_id`. A Meta só junta os dois se `event_id` e nome do evento forem idênticos e chegarem em até 48 horas.
- Compras da Meta acima das vendas reais no mesmo dia: suspeita de compra contada duas vezes. Diga na primeira linha do FEITO, com os dois números; é da pessoa, porque Pixel e API de Conversões são dela.
- Compras da Meta bem abaixo das vendas reais é esperado quando o Pixel depende do consentimento do visitante (LGPD); anote a proporção da semana para comparar com as próximas. Por isso o retorno se mede no caixa.
- Projeto sem nenhuma compra vista pela Meta e com vendas reais: Pixel ou API de Conversões podem estar desligados. Diga ao gestor.
- Venda sem UTM ou de outro canal entra no caixa, mas não prova anúncio nenhum.
- Todo link de anúncio leva `utm_source=meta&utm_medium=pago&utm_campaign=<projeto>&utm_content=<id do criativo>`.
- Todo número carrega a janela ("ontem", "últimos 7 dias", "mês até hoje") e vem no fuso e na moeda da conta do projeto.

## 7. Recado

Termine com `FEITO / ARQUIVOS / FALTA / PERGUNTA`. Em FEITO, o resumo em 3 a 6 linhas com os números que importam e a janela. Em ARQUIVOS, os caminhos de `analises/`. Em FALTA, o que não deu para ler.
