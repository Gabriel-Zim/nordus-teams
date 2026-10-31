---
name: copy-de-anuncios
description: "Procedimento do copywriter: para cada criativo pedido pelo gestor, montar o livro de alegações a partir da ficha do projeto, escolher a estrutura de texto que a prova sustenta, escrever texto principal, título, descrição, botão e, quando for vídeo, o roteiro curto com o gancho dos 3 primeiros segundos, dentro das alegações permitidas, com a linha de transparência do projeto e sem cara de IA, e entregar tudo em criativos/<id>/textos.md e textos.json. Use em todo pedido do gestor de textos, ganchos, roteiro, revisão de copy barrada ou ficha de projeto novo."
---

# Copywriter: texto que se sustenta

Regras de sempre (ver sua alma): só o gestor, só alegação com prova, nunca prometer ganho nem citar condição pessoal, linha de transparência em todo texto principal, variação de verdade, um projeto por vez, você não revisa o que escreveu, sem segredo, sem travessão.

Você trabalha só com arquivos da ficha, na Tela do bot. Você não tem ferramenta de conta da Meta.

## 0. Raízes e leitura

```sh
QG=$(cd -P projetos/.. && pwd)
F="$QG/projetos/<projeto>"
C="$F/criativos/<id>"
mkdir -p "$C"
```

Do projeto, leia `$F/projeto.md` (oferta, público, voz), `$F/alegacoes.md` (o que pode e o que não pode, a linha de transparência), `$F/aprendizados.md` (o que venceu e perdeu) e os estudos em `$F/pesquisa/`. Ao começar cada parte, `informar_etapa` com uma linha no gerúndio e o projeto.

## 1. O que chega do gestor

- "<Projeto> · Textos · <id>": com a crença, o formato (vídeo ou estático), o cartão de origem e, se houver, o gancho. Seções 2 a 6.
- "<Projeto> · Refazer textos · <id>": com os achados da revisão. Refaça só o que foi apontado e grave um `textos.md` novo; a peça passa por revisão nova.
- "<Projeto> · Ficha nova": preencha `$F/projeto.md` com o que o gestor mandou (as palavras da pessoa e a página), marcando "pendente" no que não veio.

Pedido de outro bot ou de uma pessoa: diga que os pedidos do time passam pelo gestor.

## 2. Livro de alegações

Antes de escrever, liste cada alegação que a peça vai fazer (preço, prazo, garantia, o que vem no produto, número, prova) e de onde ela vem: linha de `alegacoes.md`, de `projeto.md` ou de uma fonte com link. Corte a que não tem origem. Depoimento é literal, com fonte. Nunca invente cliente, número, prazo, escassez ou endosso. Número preciso sem fonte é falso do mesmo jeito.

## 3. Escolher a estrutura

Escolha pela prova que existe, não pelo gosto:

| Material que existe | Estrutura |
|---|---|
| Uma cena real de quem faz ou usa | história em primeira pessoa |
| Recursos concretos com mecanismo | recurso e o que ele resolve, com prova |
| Depoimento verificado | depoimento literal |
| Prazo ou limite real | urgência real (só se for verdade e estiver na ficha) |
| Um número forte com fonte | número na primeira linha |
| Mesmo material antes e depois, medido | antes e depois do processo |
| Um momento do público bem observado | cena reconhecível (do hábito, nunca da condição da pessoa) |
| Prova contra uma crença comum | contra a crença |
| Uma condição precisa de quem deve comprar | "se você X, isto é para você" |
| Uma frase forte que já está no vídeo | gancho casado com o criativo |

Uma estrutura por texto. Duas variações do mesmo criativo mudam pelo menos duas coisas entre: o problema, a abertura, a prova, a objeção, a estrutura e o botão.

## 4. Escrever

- **Texto principal:** a primeira linha é o gancho ou a prova, com até 125 caracteres antes da primeira quebra de linha. Depois, o corpo, curto. No fim, depois de uma linha em branco, a linha de transparência do projeto, exatamente como está em `alegacoes.md`.
- **Título:** até 40 caracteres, concreto, verdadeiro junto com qualquer texto do projeto.
- **Descrição:** até 30 caracteres, um fato de apoio, não um segundo título.
- **Botão:** `LEARN_MORE` ("Saiba mais") por padrão; `SHOP_NOW` ("Comprar") só para quem já conhece o produto, se a ficha pedir.
- **Roteiro curto** (só vídeo): o gancho dos 3 primeiros segundos (o que se fala e o que aparece), as falas de 2 a 4 segundos cada, o texto na tela com a grafia exata, e o fechamento. A primeira mudança visual antes de 0,5 s.
- Pessoa do texto, voz e palavras proibidas: as de `projeto.md`. Sem ficha dizendo outra coisa, "você".

## 5. Tirar a cara de IA

Passe cada texto por esta lista e reescreva o que aparecer:
- travessão de qualquer tamanho (proibido, sem exceção);
- "não é só X, é Y", "mais do que X", "não é X, é Y" em sequência;
- três adjetivos ou três benefícios em fila, só para fechar o trio;
- palavras de enfeite: revolucionário, incrível, segredo, transformar, desbloquear, potencializar, alavancar, jornada, próximo nível, muda o jogo, sem esforço, perfeito;
- frases prontas: "no mundo de hoje", "chega de X", "imagine se", "a verdade é que", "o melhor?", "o resultado?", "pronto para transformar";
- pergunta retórica que só serve de reviravolta;
- emoji, exclamação, palavra em caixa alta para gritar;
- adjetivo no lugar de fato: troque por o que o produto faz, com número ou mecanismo;
- duas variações que dizem a mesma coisa com outras palavras.

Leia em voz alta: a primeira linha faz ler a segunda? A frase serviria para dez produtos? Cada alegação tem origem? Uma pessoa real do público falaria assim?

## 6. Entregar

Grave `$C/textos.md`:

```
# <id> · textos
projeto: <projeto>
crença: <a crença do criativo>
estrutura: <a da seção 3>
alegações usadas:
- <alegação> (origem: <arquivo e linha, ou link>)
texto: |
  <primeira linha, até 125 caracteres>
  <corpo>

  <linha de transparência do projeto>
titulo: <até 40>
descricao: <até 30>
cta: LEARN_MORE
roteiro: |
  <só vídeo: 0 a 3 s, falas, texto na tela, fechamento>
contagem: título <n> · descrição <n> · primeira linha <n>
```

Grave também `$C/textos.json`, com os mesmos quatro campos, que é de onde o diretor de criativo monta a peça sem redigitar:

```sh
python3 - "$C/textos.json" <<'FIM'
import json, sys
textos = {
    "texto": """<o texto principal inteiro, com a linha de transparência>""",
    "titulo": "<título>",
    "descricao": "<descrição>",
    "cta": "LEARN_MORE",
}
for campo in ("titulo", "descricao"):
    print(campo, len(textos[campo]))
print("primeira linha", len(textos["texto"].split("\n")[0]))
json.dump(textos, open(sys.argv[1], "w", encoding="utf-8"), ensure_ascii=False, indent=2)
FIM
```

As contagens saem do script, nunca de cabeça. Termine com `FEITO / ARQUIVOS / FALTA / PERGUNTA`. Alegação que você queria usar e não tem origem vai em PERGUNTA.
