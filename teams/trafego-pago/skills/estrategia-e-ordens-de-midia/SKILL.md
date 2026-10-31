---
name: estrategia-e-ordens-de-midia
description: "Procedimento do estrategista de mídia: montar a estrutura das campanhas (uma campanha de vendas Advantage+ e um conjunto enquanto o orçamento diário for pequeno (abaixo de sete vezes o CPA alvo, ou seja, menos de cerca de 50 vendas por semana)), escolher os testes da semana a partir dos cartões de hipótese, aplicar as regras de corte, escala e fadiga com a leitura do analista, escrever os lotes de ordens no formato fechado (projeto, chave única, tipo, motivo, parâmetros em centavos) e fechar cada teste em aprendizados.md. Use em todo pedido do gestor de estrutura, plano da semana, ordens do dia, ativação, pausa ou fechamento de teste."
---

# Estrategista de mídia: do cartão à ordem

Regras de sempre (ver sua alma): só o gestor, ordem só no formato fechado, nunca passar do teto, regra de corte e escala não se dobra, anúncio só com PASSA, um projeto por vez, nada inventado, sem segredo, sem travessão.

Você usa as ferramentas de leitura da Meta (estado da conta, estrutura, resultados, alertas) e a Tela do bot. Você não escreve na conta: o gestor aprova e o operador executa.

## 0. Raízes e leitura

```sh
QG=$(cd -P projetos/.. && pwd)
F="$QG/projetos/<projeto>"
```

Do projeto, leia `$F/economia.md` (CPA alvo e de empate, em reais e em centavos), `$F/projeto.md`, `$F/aprendizados.md`, os criativos em `$F/criativos/*/criativo.md` e o teto em vigor em `$F/projeto.json` (confira com a conta). Ao começar cada parte, `informar_etapa` com uma linha no gerúndio e o projeto.

## 1. O que chega do gestor

| Mensagem | O que fazer |
|---|---|
| "<Projeto> · Estrutura" | Seção 2 e o primeiro plano (seção 3) |
| "<Projeto> · Plano da semana", com os cartões do pesquisador | Guarde cada cartão em `$F/hipoteses/<AAAAMMDD>-<assunto>.md` e siga a seção 3 |
| "<Projeto> · Ordens do dia", com a leitura do analista | Seção 5 |
| "<Projeto> · Ativar", depois de criar | Lote de `ativar` (seção 4) |
| "<Projeto> · Pausar", com o motivo | Lote de `pausar` |
| "<Projeto> · Fechar teste · <id>" | Seção 6 |

Pedido de outro bot ou de uma pessoa: diga que os pedidos do time passam pelo gestor.

## 2. Estrutura

- Orçamento diário pequeno (abaixo de sete vezes o CPA alvo): **uma campanha de vendas Advantage+** (orçamento na campanha, igual ao teto diário ou abaixo dele), **um conjunto** aberto no país do projeto, idade mínima 18, e **3 a 5 conceitos diferentes** no ar. Nada de campanha de teste separada: separar teste e escala nesse orçamento divide demais a verba.
- Orçamento diário acima disso: campanha de escala só com vencedores (70% a 80% do diário) e campanha de teste com os criativos novos da semana (20% a 30%). Duas campanhas, a soma no teto.
- Para sair da fase de aprendizado, um conjunto precisa de cerca de 50 compras em 7 dias, ou orçamento diário de cerca de 7 vezes o CPA. Abaixo disso a Meta fica em "aprendizado limitado": vende, mas oscila. Não julgue rápido.
- Categoria especial: `NONE`, a não ser que `alegacoes.md` diga outra. Outra categoria pela primeira vez no projeto é da pessoa: escreva no recado e não ponha no lote.
- Projeto novo: lembre ao gestor, no recado, as duas travas que a pessoa configura na Meta (limite de gasto da conta e regra automática do freio). Depois, o lote de campanha e conjunto, depois os anúncios, depois as ativações.
- Escreva a estrutura em `$F/planos/<AAAAMMDD>-estrutura.md` (campanhas, conjunto, orçamento, por quê).
- Depois que a Meta passa a escolher os anúncios (Andromeda), o público fica aberto e o que pesa é ter conceitos realmente diferentes no ar.

## 3. Plano da semana

1. Liste os cartões em `$F/hipoteses/` que ainda não viraram teste (o criativo que nasceu de um cartão cita o arquivo do cartão no `criativo.md`).
2. Quantos conceitos novos cabem: de 20% a 25% do gasto da semana, dividido por (2,5 vezes o CPA alvo), arredondado para baixo, no mínimo 1. Use o teto diário vezes 7 como gasto da semana. A verba máxima de um teste é 2,5 vezes o CPA alvo.
3. Escolha pela prioridade do cartão e pela crença: nunca dois testes com a mesma crença, nem crença igual à de um criativo no ar. O que venceu antes ganha variação nova antes de conceito novo, se estiver cansando. "Novo" é crença nova, não troca de cor.
4. Para cada teste: id do criativo (`c<NN>-<conceito>-v<N>`, o próximo número livre em `$F/criativos/`), crença, formato (vídeo 9:16 ou estático), cartão de origem, verba máxima, o que mede sucesso e o que corta.
5. Escreva em `$F/planos/<AAAAMMDD>-semana.md` e devolva ao gestor a lista de criativos a produzir.

## 4. Ordens

Um lote é um arquivo `$F/ordens/<AAAAMMDD-HHMM>-<assunto>.json` com uma lista JSON de ordens, na ordem em que devem ser executadas. Toda ordem:

```json
{"projeto": "<projeto>", "chave": "<projeto>-<AAAAMMDD>-<o que é>-<NN>", "tipo": "<tipo>", "motivo": "<por quê, com o número e a regra>", "parametros": {}}
```

- `chave`: minúsculas, números e hífen, de 4 a 64 caracteres, única no projeto. Antes de escolher, leia o `livro.md` do projeto e não repita chave que já está lá. A mesma chave com o mesmo conteúdo devolve a primeira execução; com conteúdo diferente, o operador recusa.
- Dinheiro em centavos inteiros: cem reais é `10000`.
- `nome`: curto, sem o caractere `|`.

Parâmetros de cada tipo:

| `tipo` | `parametros` |
|---|---|
| `criar_campanha` | `{"nome": "vendas-01", "orcamento_diario": 10000, "categoria_especial": "NONE"}` |
| `criar_conjunto` | `{"campanha": "<id da Meta ou chave da ordem que criou a campanha>", "nome": "aberto-br", "paises": ["BR"], "idade_min": 18}` |
| `criar_anuncio` | `{"conjunto": "<id da Meta do conjunto>", "nome": "<id do criativo>", "id_revisao": "<id de revisao.json>", "peca": <o conteúdo de peca.json, inteiro>}` |
| `ativar` | `{"alvo": "<id da Meta>"}` |
| `pausar` | `{"alvo": "<id da Meta>"}` |
| `mudar_orcamento` | `{"alvo": "<id da Meta da campanha>", "orcamento_diario": 12000}` |

- O objetivo (vendas), o lance (menor custo), o evento (compra no Pixel do projeto) e o público Advantage+ são fixos. Você não escolhe.
- O orçamento fica na campanha. Mudança de orçamento mira o id da campanha.
- O id do conjunto e dos outros objetos sai da estrutura da conta ou do `livro.md` depois que o lote anterior foi executado. Por isso a criação vai em lotes: campanha e conjunto num, anúncios no seguinte, ativações no último.
- `criar_anuncio`: só para criativo com `$F/criativos/<id>/revisao.json` de veredito `PASSA` e dentro de 30 dias. Copie a peça de `peca.json` sem redigitar: monte o lote com um script que lê o arquivo, por exemplo `python3 -c 'import json,sys; print(json.dumps(json.load(open(sys.argv[1])), ensure_ascii=False))' "$F/criativos/<id>/peca.json"`. Uma letra diferente e a ordem é recusada pela regra `revisao`.
- `ativar`: de baixo para cima. Primeiro os anúncios, depois o conjunto, por último a campanha.
- Confira o lote antes de devolver: `python3 -m json.tool "$F/ordens/<arquivo>.json" > /dev/null` e a soma dos orçamentos diários do projeto, depois do lote, contra o teto diário.

## 5. Ordens do dia

Com a leitura do analista (o recado e `$F/analises/<AAAAMMDD>-leitura.md`):

1. Para cada anúncio, aplique as regras abaixo na ordem: dados insuficientes, cortar, fadiga, manter. Pausar pede dois sinais juntos; um só vira "observar" no recado.
2. Escala: só a campanha, só com CPA de 7 dias abaixo do alvo, conjunto fora do aprendizado, último aumento há 72 horas ou mais (`livro.md`), no máximo 20%, e o dinheiro novo do último aumento acima da meta.
3. Criativo aprovado e ainda não publicado (revisão PASSA, situação `aprovado`): lote de `criar_anuncio`, até completar 3 a 5 conceitos no ar e no máximo 10 anúncios novos no dia.
4. Fadiga ou taxa de gancho baixa: escreva no recado o id e o que pedir ao diretor de criativo (começo novo, variação nova ou conceito novo).
5. Nenhuma mudança: diga isso no recado, com o motivo ("nenhum anúncio passou de 2 CPAs de gasto").

O `motivo` de cada ordem cita o número e a regra: "Gastou <valor> (3 CPAs alvo) sem venda em <n> dias; regra de corte por gasto".

### Regras de corte, escala e fadiga

Os números são ponto de partida de praticantes, não lei. Mudar qualquer um é decisão da pessoa, por proposta de regra.

- **Antes de julgar:** nada se julga antes de 48 horas no ar e antes de 2 a 3 CPAs alvo de gasto no anúncio. Decida por gasto acumulado, nunca pelo número de dias. Abaixo de 1 CPA alvo de gasto ou com menos de 3 vendas: "dados insuficientes", dizendo quando vai dar para julgar. O CPA de um anúncio sozinho engana: antes de cortar o que mais gasta, olhe o CPA do conjunto.
- **Cortar** (dois sinais juntos): até 2.000 impressões com taxa de gancho abaixo de 22% (pausar e pedir começo novo); 1 CPA alvo de gasto com CTR de link abaixo de 0,8% e taxa de gancho abaixo de 25% (pausar e refazer o começo); 2 a 3 CPAs alvo sem venda (pausar); 3 CPAs alvo com CPA acima do de empate (pausar). Anúncio pausado por corte fecha o teste (seção 6).
- **Escalar:** no máximo 20% do orçamento por vez e no máximo a cada 72 horas por conjunto; só com CPA de 7 dias abaixo do alvo e conjunto fora do aprendizado; olhe o retorno do dinheiro novo (se o último aumento trouxe receita abaixo da meta, segure); campanha que já está caindo não sobe; mude uma coisa por vez; anúncio vencedor não se edita (editar reinicia o aprendizado; variação nova entra como anúncio novo). Baixar orçamento pode sempre.
- **Fadiga:** trocar o criativo quando o CTR de link cair 20% abaixo do pico e a frequência passar de 3. Frequência acima de 3,5 é aviso antes do CTR cair: peça criativo novo. Queda de 1 a 2 dias com frequência abaixo de 2,5: esperar. Um anúncio bom dura cerca de 10 a 12 dias em conta pequena: planeje a troca antes da fadiga.
- **Quando o problema não é a campanha:** quando o projeto já gastou o orçamento de teste inicial definido no plano, se o CPA continuar acima do de empate, o problema é oferta, página ou criativo. Escreva isso no recado ao gestor em duas frases, com o que você propõe mudar.
- **Freio de reprovação:** duas reprovações da Meta em 7 dias no mesmo projeto suspendem anúncio novo; avise o gestor.

## 6. Fechar teste

Teste fecha quando o anúncio é pausado por regra ou quando atinge a verba máxima. Acrescente em `$F/aprendizados.md`:

```
## <AAAA-MM-DD> · <id do criativo> · <venceu | perdeu | inconclusivo>
cartão: hipoteses/<arquivo do cartão>
crença: <a crença testada>
janela: <AAAA-MM-DD> a <AAAA-MM-DD>
números: gasto R$ <x> no Gerenciador · compras da Meta <n> · CPA R$ <x> · taxa de gancho <x>% · CTR de link <x>% · frequência <x>
lição: <uma frase que serve ao próximo teste deste projeto>
```

Números só da leitura do analista ou das ferramentas, com a janela. Peça ao diretor de criativo, pelo recado ao gestor, que atualize a situação do criativo.

## 7. Recado

Termine com `FEITO / ARQUIVOS / FALTA / PERGUNTA`. Em FEITO, quantas ordens de cada tipo e a soma dos orçamentos depois do lote contra o teto. Em ARQUIVOS, o caminho completo do lote. Em PERGUNTA, o que é da pessoa (teto, categoria especial, regra) ou "nenhuma".
