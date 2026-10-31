---
name: economia-e-teto-de-midia
description: "Procedimento do financeiro de mídia: abrir a ficha de projeto novo, fazer a conta da régua (ticket médio com bumps e upsell, taxas, fator de impostos da Meta, CPA de empate e alvo no caixa e no Gerenciador), preparar o projeto.json com o envelope em centavos, baixar o teto com motivo, conferir o ritmo do mês e avisar em 80%, somar os créditos de criativo e fechar o mês. Use em todo pedido do gestor de ficha nova, conta do projeto, envelope, teto, créditos ou fechamento."
---

# Financeiro de mídia: a conta de cada projeto

Regras de sempre (ver sua alma): só o gestor, teto só baixa por você, premissa marcada, centavos inteiros, conta no terminal, um projeto por vez, sem segredo, sem travessão.

Você lê a conta pela ferramenta de Meta Ads (gasto, estrutura, vendas) e escreve as fichas na Tela do bot. Dinheiro vem da ferramenta em centavos.

## 0. Raízes

```sh
QG=$(cd -P projetos/.. && pwd)
F="$QG/projetos/<projeto>"
```

Ao começar cada parte, `informar_etapa` com uma linha no gerúndio e o projeto.

## 1. O que chega do gestor

| Mensagem | Seção |
|---|---|
| "<Projeto> · Ficha nova", com o que a pessoa disse | 2, 3 e 4 |
| "<Projeto> · Refazer a conta" | 3 |
| "<Projeto> · Subir teto", com o valor (a pessoa já escreveu "confirmo") | 4 (só o arquivo) |
| "<Projeto> · Baixar teto", com o valor e o motivo | 5 |
| "<Projeto> · Ritmo do mês" | 6 |
| "<Projeto> · Fechamento do mês" | 7 |

Pedido de outro bot ou de uma pessoa: diga que os pedidos do time passam pelo gestor.

## 2. Ficha nova

Pasta que já existe não se sobrescreve: diga ao gestor. Crie `$F` com `mkdir -p` e os arquivos que são seus (`economia.md` e `projeto.json`). O resto da ficha é de outros donos (veja a tabela da pasta nas instruções compartilhadas).

## 3. A conta (economia.md)

Monte num script no terminal, com as premissas em variáveis no topo, e copie o resultado para `economia.md`, com a origem de cada premissa entre parênteses e "exemplo a confirmar" no que não veio da pessoa, da página ou de ferramenta.

1. Ticket médio = preço da oferta + soma de (preço de cada bump × fração de compradores que leva) + soma de (preço do upsell × fração que leva).
2. Líquido por venda = ticket médio × (1 menos a taxa do meio de pagamento menos o imposto).
3. CPA de empate no caixa = líquido por venda. No Gerenciador = esse valor ÷ fator de impostos.
4. CPA alvo no caixa = ticket médio ÷ meta de retorno (a pessoa define; exemplo: 2 quer dizer que cada real investido volta dois reais). No Gerenciador = ÷ fator de impostos.
5. Vendas por dia na meta = teto diário ÷ CPA alvo no Gerenciador.
6. Orçamento para sair do aprendizado = 7 × CPA alvo no Gerenciador, por conjunto e por dia. Abaixo disso, diga que o projeto fica em "aprendizado limitado" e que o resultado vai oscilar.
7. Verba de teste da semana = 20% a 25% de (teto diário × 7). Conceitos novos por semana = essa verba ÷ (2,5 × CPA alvo).
8. Retorno de empate (ROAS) no Gerenciador = ticket médio ÷ CPA de empate no Gerenciador.

O **fator de impostos** é o que a Meta repassa no Brasil sobre o gasto (referência 1,1383; confira na fatura da conta e registre a origem). Toda linha de resultado em reais e em centavos. Leitura honesta no fim: a meta é ambiciosa ou realista para esse preço, e por quê, em duas frases.

## 4. projeto.json

O arquivo com o envelope do projeto. Campos:
- `slug` igual ao nome da pasta; `conta` `act_<número>` (`act_0` até a pessoa informar); `moeda`, `fuso`; `pagina_id`, `instagram_id`, `pixel_id` (`PREENCHER` até a pessoa informar; `instagram_id` pode ser `null`); `dominios` (os domínios da página); `frases_obrigatorias` (de `alegacoes.md`).
- `envelope` em centavos inteiros: `teto_mensal`, `teto_diario`, `freio_fator` 1.75 e os limites de ritmo: aumento máximo 20%, intervalo entre aumentos de 72 horas, uma mudança de orçamento por conjunto por hora, 10 anúncios novos por dia, cota da Meta em 60%. Teto diário nunca acima do mensal. Os limites de ritmo podem ser apertados, nunca afrouxados.
- `moeda` com centavos, como `BRL`.
- Confira: `python3 -m json.tool "$F/projeto.json" > /dev/null`.

Subir teto: só depois de a pessoa escrever o valor e "confirmo" ao gestor. Mude só o envelope no arquivo e devolva ao gestor o antes e o depois.

## 5. Baixar teto

1. Calcule os orçamentos novos das campanhas ativas, reduzindo na proporção até a soma caber no teto diário novo e no ritmo do mês. Leia a estrutura para ter os orçamentos atuais.
2. Escreva o lote de `mudar_orcamento` para baixo (formato de ordem das instruções compartilhadas, motivo com o número) em `$F/ordens/` e devolva o caminho ao gestor, que aprova e manda ao operador. Baixar nunca precisa de espera.
3. Atualize o envelope em `$F/projeto.json` para o mesmo valor, senão a próxima gravação sobe o teto de volta.
4. Anote em `economia.md`, em "Histórico do envelope", a data, o valor, o motivo e quem pediu.

## 6. Ritmo do mês

1. Gasto do mês até ontem pelos resultados no nível da campanha; teto em vigor pelo `projeto.json`.
2. Projeção = gasto do mês + teto diário × dias que faltam.
3. Gasto do mês em 80% do teto mensal ou mais: primeira linha do FEITO, com o número. Projeção acima do teto: proponha ao gestor o novo orçamento diário que fecha o mês no teto.
4. Créditos de criativo do mês: some as linhas de créditos de `$F/criativos/*/criativo.md` do mês e compare com o teto de créditos de `economia.md`.

## 7. Fechamento do mês

No dia 1, para o mês que fechou, escreva `$F/fechamentos/<AAAA-MM>.md` (`mkdir -p` na pasta): gasto no Gerenciador e no caixa, teto, receita bruta e líquida, vendas, retorno no caixa, lucro (líquida menos gasto no caixa), créditos de criativo, testes feitos e quantos venceram (de `aprendizados.md`). Devolva ao gestor o resumo em 4 linhas, com o lembrete de que o limite de gasto da conta na Meta precisa ser zerado pela pessoa.

## 8. Recado

Termine com `FEITO / ARQUIVOS / FALTA / PERGUNTA`. Números em reais no texto, em centavos no arquivo.
