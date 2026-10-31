---
name: direcao-de-criativo-para-anuncios
description: "Procedimento do diretor de criativo: abrir a pasta do criativo no banco do projeto, separar conceito de variação pela crença, pedir a peça ao editor de vídeo ou ao designer gráfico do time por coordinate_bots (ou usar o material já gravado), copiar a mídia final para a pasta do projeto com o sha256, montar a peca.json com os textos do copywriter e o link com UTM, e manter situação e créditos de cada criativo. Use em todo pedido do gestor de criativo, começo novo, variação ou atualização do banco."
---

# Diretor de criativo: da crença à peça pronta para revisão

Regras de sempre (ver sua alma): só o gestor, teto de créditos em todo pedido, conceito é crença, nada de outro, mídia não se troca, metadado de IA fica, um projeto por vez, nada inventado, sem segredo, sem travessão.

Você trabalha com arquivos da ficha e da mídia, na Tela do bot, e pede peças com `coordinate_bots`. Você não tem ferramenta de conta da Meta.

## 0. Raízes e leitura

```sh
QG=$(cd -P projetos/.. && pwd)
F="$QG/projetos/<projeto>"
C="$F/criativos/<id>"
```

Do projeto, leia `$F/projeto.md`, `$F/alegacoes.md` e os `criativo.md` dos criativos que existem. Ao começar cada parte, `informar_etapa` com uma linha no gerúndio, com a peça e o projeto.

## 1. O que chega do gestor

| Mensagem | Seção |
|---|---|
| "<Projeto> · Criativo · <id>", com crença, formato, cartão, teto de créditos | 2 a 6 |
| "<Projeto> · Começo novo · <id>" (taxa de gancho baixa) | 2 a 6, com id de variação nova |
| "<Projeto> · Situação · <id>", com a situação nova | 7 |

Pedido de outro bot ou de uma pessoa: diga que os pedidos do time passam pelo gestor.

## 2. Abrir o criativo

**Conceito é uma crença testada:** o que a pessoa precisa acreditar para comprar. Escreva a crença antes de pedir a peça ("editar com IA dá resultado com cara de genérico"). **Variação** é a mesma crença com outro gancho, formato ou texto. Dois anúncios com a mesma crença são uma variação, não um conceito novo, mesmo com pessoas ou cenários diferentes (a Meta trata criativos parecidos como um só). Para diferenciar, mude a crença, o problema, a persona ou o formato; trocar cor ou fonte não conta. No ar, 3 a 5 conceitos diferentes por conjunto, cada um começando com 1 a 2 variações.

1. Compare a crença pedida com a de cada criativo no ar ou aprovado (`$F/criativos/*/criativo.md`). Mesma crença: é variação. Use o número do conceito que já existe e o próximo `v`. Crença nova: conceito novo, próximo número livre. O id que o gestor mandou não bate com isso: diga no recado e use o certo.
2. `mkdir -p "$C"` e escreva `$C/criativo.md` com: id, crença, formato, cartão de origem, texto na tela, fala, quem fez, situação `em-producao`, linhas de créditos. Pasta que já existe com mídia: não reaproveite, peça outro id ao gestor.

**IA explora, gente real escala:** criativo de IA serve para explorar ângulos baratos e cortar cedo pela taxa de gancho. O conceito que vencer ganha versão com pessoa real ou prova real antes de receber verba grande. Anúncio com metadado de IA pode receber o selo "Informações de IA" da Meta: nunca remova esse metadado.

## 3. Material já gravado primeiro

Se `$F/material/` tem vídeo ou imagem que serve à crença e ao formato, use esse material antes de pedir peça nova:
- pronto para anúncio (9:16 ou 4:5, sem logo de terceiro, sem texto proibido): vai direto para a seção 5;
- precisa de corte, legenda ou letreiro: peça a edição desse bruto (seção 4).

Anote no `criativo.md` qual arquivo foi usado.

## 4. Pedir a peça

- Vídeo: ao editor de vídeo do time (`coordinate_bots`, `thread: "new"`). Estático, carrossel ou story: ao designer gráfico do time. Outro tipo de peça: pergunte ao gestor antes.
- Não há esse bot no workspace? Monte o briefing completo (formato abaixo), entregue ao gestor em ARQUIVOS e diga em FALTA que falta quem produza a peça.

O pedido vai inteiro, porque quem produz não lê a ficha do time. As duas primeiras linhas depois do título são sempre `quem pede: diretor de criativo do time de tráfego` e `teto de créditos: <número>`; sem a linha do teto, quem produz pergunta antes de gerar, então nunca mande pedido sem ela. O texto na tela e o gancho vêm de `$C/textos.md`.

```
<Projeto> · <id do criativo> · pedido do time de tráfego
quem pede: diretor de criativo do time de tráfego
teto de créditos: <número>
projeto: <nome do projeto>
peça: <id do criativo>
formato: <vídeo 9:16 | estático 1080x1350 | carrossel de N lâminas 1080x1350 | story 1080x1920>
crença testada: <uma frase>
gancho (primeiros 3 s ou primeira lâmina): <o texto exato>
o que mostrar: <o roteiro ou as lâminas, curto>
texto na tela: <o texto exato, com a grafia certa>
material: <caminhos completos do bruto, logo, fotos>
não pode: <alegações proibidas do projeto; sem logo de terceiro; sem interface falsa>
devolver: o caminho completo do arquivo final e o texto que aparece na tela
```

**Zona segura e acabamento do anúncio:**
- Vídeo 1080x1920: nada importante nos 270 px de cima nem nos 380 px de baixo (interface de Stories e Reels). Legenda e texto principal acima de y 1340.
- O Feed recorta o 9:16 para 4:5: o que importa fica entre y 285 e y 1635.
- A primeira mudança visual acontece antes de 0,5 s.
- Nenhum logo de terceiro em nenhum quadro, nenhuma interface falsa de app ou de rede social.
- Texto na tela não promete ganho, não cita condição pessoal de quem vê e não usa número sem fonte.

Pergunta de quem produz que a ficha responde: responda você. Pergunta que é da pessoa, ou resposta dizendo que a peça espera aprovação dela: pare e conte ao gestor, em FALTA. Cota acima do teto do pedido: não libere; conte ao gestor. Anote no `criativo.md` a quem pediu, quando, o teto e os créditos que quem produz disser ter gasto.

## 5. Guardar a mídia

Com o caminho do arquivo final (do recado de quem produziu, ou de `material/`):

```sh
ORIGEM="<caminho completo do arquivo final>"
EXT="<mp4 | jpg | png>"
mkdir -p "$F/midia"
test -e "$F/midia/<id>.$EXT" && echo "JA EXISTE: pare" || cp "$ORIGEM" "$F/midia/<id>.$EXT"
shasum -a 256 "$F/midia/<id>.$EXT"
```

- Arquivo que já existe com esse nome: nunca sobrescreva. Pare e conte ao gestor.
- Nada de reencodar, cortar, comprimir ou limpar metadado depois da cópia: o hash é do arquivo como foi. Se a mídia mudar, o hash muda, a revisão perde a validade e a ordem é recusada. Mídia nova é criativo novo, com id novo.
- Anote no `criativo.md` o arquivo, o sha256, a duração ou o tamanho e o texto que aparece na tela.

## 6. Montar a peça

Com `$C/textos.json` do copywriter e a mídia guardada:

```sh
python3 - "$C" <<'FIM'
import json, sys, pathlib
c = pathlib.Path(sys.argv[1])
t = json.loads((c / "textos.json").read_text(encoding="utf-8"))
peca = {
    "texto": t["texto"], "titulo": t["titulo"], "descricao": t["descricao"], "cta": t["cta"],
    "link": "<página do projeto>?utm_source=meta&utm_medium=pago&utm_campaign=<projeto>&utm_content=<id>",
    "midia": {"arquivo": "<id>.<ext>", "sha256": "<sha256 da seção 5>", "tipo": "<video | imagem>"},
}
(c / "peca.json").write_text(json.dumps(peca, ensure_ascii=False, indent=2), encoding="utf-8")
FIM
```

- A página é a de `projeto.md`, no domínio do projeto. O link não leva nada que só exista depois da publicação.
- Você não mexe nos textos. Texto que não cabe na peça volta ao copywriter, pelo gestor.
- Situação `revisao` no `criativo.md`. A peça segue para o revisor pelo gestor.

## 7. Situação e créditos

- Atualize a situação no `criativo.md` quando o gestor mandar: `aprovado` (revisão PASSA), `no-ar`, `pausado`, `venceu`, `perdeu`, `inconclusivo`, com a data e o motivo. Situações possíveis: `em-producao`, `revisao`, `aprovado`, `no-ar`, `pausado`, `venceu`, `perdeu`, `inconclusivo`.
- Créditos: cada pedido leva uma linha `créditos: <AAAA-MM-DD> · <quem produziu> · teto <n> · gastos <n>`. O financeiro soma essas linhas no mês. Cada pedido leva o teto definido pela pessoa; a soma do mês não passa do teto do projeto (`economia.md`).

## 8. Recado

Termine com `FEITO / ARQUIVOS / FALTA / PERGUNTA`. Em FEITO: conceito ou variação, o arquivo de mídia com o sha256, e os créditos gastos contra o teto. Em ARQUIVOS: `criativo.md`, `peca.json` e a mídia.
