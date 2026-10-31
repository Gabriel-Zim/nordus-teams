---
name: geracao-de-imagem-com-ia
description: "Procedimento do designer de IA para criar imagens pelo Zim Studio: ler o pedido e o padrão do cliente, escolher o caminho (foto nova de contexto genérico, melhora de foto real, render que vira foto, interior em computação gráfica), enviar as imagens base, escrever o pedido como diretor de fotografia, gerar ou editar com modelo explícito e chave de idempotência, acompanhar sem reenviar por demora, conferir cada imagem contra a original e entregar os arquivos na pasta do pedido. Use em todo pedido de imagem."
---

# Geração de imagem com IA: do pedido ao arquivo

Siga as etapas na ordem. Você entrega só imagem (foto, fundo, textura, objeto, cena), nunca lâmina com texto. Regras que valem em todas as etapas: um cliente por pedido, foto real para produto, obra, imóvel ou pessoa do cliente, render nunca redesenhado, sem texto nem logo dentro da imagem, sem publicar, sem travessão (veja a sua alma).

## Pré-requisito: Zim Studio conectado

Se as ferramentas do Zim Studio não aparecem para você, não gere nada por outro caminho: explique à pessoa como conectar (Apps conectados, aba Conexões avançadas, ligar a conexão zim-studio e preencher o valor Authorization com a chave da conta) e peça para tentar de novo.

## Pasta de trabalho

Organize por cliente: `clientes/<cliente>/` com o cartão do cliente (`ficha.md`: paleta em hex, "tom de foto", regras), as receitas dele (`receitas.md`: frases obrigatórias de prompt e o que já funcionou) e as fotos reais; e `entregas/<cliente>/<pedido>/imagens/` para o que você gera, com um `registro.md`.

**Referência de pesquisa não entra na peça.** Imagens de outros autores achadas em pesquisa servem de inspiração e nunca entram como imagem, como referência enviada ao Zim Studio nem como base de edição. Leve para o pedido só o princípio (luz, enquadramento, clima), descrito em palavras.

## 1. Ler o pedido e as receitas

O pedido deve trazer, por imagem: nome, uso (lâmina e tratamento), tamanho final, área calma para o texto, foto base (ou "nenhuma"), receita e direção, e a pasta onde salvar. Leia:

1. As receitas e o "tom de foto" do cliente (mandam sobre as regras gerais quando divergem), a paleta e as regras dele.
2. O briefing do pedido, para entender a peça inteira.
3. O que já foi gerado para este cliente (`registro.md` das entregas dele). Não repita conceito, enquadramento nem cena. Só a pasta deste cliente.

Pare e avise quem pediu quando:
- pedem o produto, a obra, o imóvel ou uma pessoa do cliente e não há foto real como base;
- pedem para recriar por IA um logo, um mapa ou qualquer imagem com texto;
- pedem texto, número ou logo dentro da imagem.

Foto de contexto (cidade, bairro, prédio de terceiro) barrada por logo, letreiro, rosto reconhecível, placa ou marca d'água que o corte não tira: não pare esperando aprovação. Siga a saída combinada no pedido (a outra foto real, ou a imagem de contexto genérico gerada, sem marca, texto ou pessoa) e conte o que fez. Sem saída combinada, gere a imagem de contexto genérico e diga. Foto real do produto, obra ou imóvel do cliente nunca é trocada por gerada: aí avise.

## 2. Escolher o caminho

| Caso | Como | Modelo (`motor`) |
|---|---|---|
| Foto nova de contexto genérico (cidade, região, estilo de vida, objeto de luxo, textura, still) | `gerar_imagem` | modelo fotográfico (por exemplo `nano-banana-2-1`) |
| Melhorar foto real (luz, nitidez, resolução, limpeza) sem mudar o conteúdo | `editar_imagem`, a foto como primeira imagem | modelo fotográfico |
| Render do cliente vira foto real | `editar_imagem`, o render como primeira imagem, já no enquadramento final | modelo fotográfico |
| Interior 100% computação gráfica que precisa mudar | `editar_imagem` | modelo de design (por exemplo `gpt-image-2-5`) |
| A receita do cliente pede outro modelo | conforme a receita | o da receita |
| Foto do cliente precisa de outra proporção | skill `imagem-por-codigo` (quadro por código, IA só fora da foto) | modelo fotográfico |
| Mapa, infográfico, print do cliente fora da paleta | skill `imagem-por-codigo` (por código) | nenhum |
| Logo | nunca por IA; use o arquivo do cliente | nenhum |

Confirme o identificador exato do modelo na lista de modelos do Zim Studio antes da primeira geração (o nome de exibição nem sempre é o nome chamável). Passe sempre o `motor` explícito: sem ele, a geração e a edição caem em outros modelos. Passe `direcao_de_arte: false` (a direção é a sua). Qualidade 2K por padrão; 4K quando a imagem ocupa a lâmina inteira ou vai para impressão.

## 3. Mandar as imagens base ao Zim Studio

O Zim Studio recebe imagem por endereço. Arquivo local (foto real, render, quadro montado) sobe assim:

1. Calcule o tamanho em bytes e o sha256 do arquivo.
2. `solicitar_envio_de_midia` com `nome`, `papel` (`produto` para foto ou render do cliente, `referencia` para o resto), `mime_type`, `tamanho_bytes`, `sha256`, e `salvar_no_elenco: false`.
3. Envie os bytes por PUT ao endereço devolvido, com os cabeçalhos indicados na resposta.
4. `confirmar_envio_de_midia` com o ticket: ele devolve o endereço que entra em `imagens`.

Não pergunte sobre salvar personagem: a mídia fica só na biblioteca.

## 4. Gerar ou editar

**Pedido de imagem** (o `prompt` pode ser em inglês; ele não vai para pessoas). Escreva como diretor de fotografia:
- assunto específico do cliente e do tema (o detalhe que só ele tem), nunca clichê (aperto de mão, skyline ao pôr do sol, porquinho, foguete);
- lente e enquadramento; luz (hora e direção); paleta em hex do cartão; textura;
- a área calma reservada para o texto (quem pediu diz onde);
- "no text, no letters, no numbers, no logo, no watermark";
- volumes limpos em vez de vegetação ou textura fina; "flat, no bevel, no 3D" quando o estilo for plano.

**Render e foto do cliente** (edição): a original é a primeira imagem, já no enquadramento final. O prompt diz o que mudar e manda preservar o resto: "UNCHANGED architecture, materials, colors, framing, house number and landscaping; no redraw; only photographic realism". Siga também as frases obrigatórias da receita do cliente.

**Custo.** Cada geração gasta créditos. Respeite o teto que a pessoa definiu. Para um lote, cote antes (`apenas_cotar: true`), diga o valor e espere o sim. Para uma imagem avulsa, gere direto.

**Chave de cada criação:** passe sempre `chave_de_idempotencia` no formato `<cliente>-<pedido>-<nome>-v<n>` (8 a 80 caracteres; encurte o pedido se passar). Nova tentativa de uma imagem reprovada é criação nova: `v2`, `v3`.

## 5. Acompanhar até ficar pronto (nunca reenviar por demora)

A geração volta com um id antes de terminar.
- Acompanhe com `consultar_geracao` (id e espera de 25 segundos) até a situação ser pronta ou falha.
- Se uma chamada estourou o tempo ou caiu a conexão, **não reenvie**: a geração pode ter entrado. Procure com `listar_geracoes` (busca com um trecho do prompt, janela das últimas 24 horas). Achou: acompanhe aquele id. Não achou e precisa repetir: repita o mesmo pedido com a **mesma** chave de idempotência, que devolve a geração já registrada sem criar outra.
- Falhou de verdade: leia o motivo, ajuste o pedido e tente com chave nova.

Pronto: baixe o arquivo para a pasta do pedido com o nome combinado e confira tipo e tamanho.

## 6. Conferir cada imagem

A imagem vai direto ao designer gráfico (ou à pessoa), sem outra revisão no caminho: abra cada arquivo e confira.

- **Foto real preservada:** monte lado a lado com a original e compare posição, tamanho, arquitetura, materiais, cores, número da casa, canteiros. Mudou qualquer coisa: refaz. Guarde a comparação como `comparacao-<nome>.png` na pasta do pedido.
- **Cara de IA:** pele de plástico, mãos estranhas, brilho genérico, rabisco em vegetação, emenda, mancha, marca d'água, clichê.
- **Texto:** nenhuma letra, número ou logo dentro da imagem.
- **Padrão:** luz e cor do "tom de foto" do cartão; área calma onde foi pedido; resolução que aguenta o tamanho final.

Reprovou na sua conferência: refaça antes de entregar (chave nova). Correção pedida depois (num ajuste da pessoa, ou porque achou texto dentro da imagem): refaça só a mudança pedida, com a versão atual como primeira imagem ("keep its exact style, change only ..."), e confira de novo.

## 7. Registrar e entregar

Acrescente uma linha por imagem em `entregas/<cliente>/<pedido>/imagens/registro.md`:

```
| data | peça | nome | pedido resumido | modelo | chave | arquivo |
```

Termine a vez com uma resposta em texto. Para outro robô, com caminhos completos:

```
Imagens prontas
cliente: <pasta do cliente>
pedido: <caminho completo da pasta do pedido>
- <caminho completo>/imagens/lamina-fundo.png: lâmina 1, render virou foto, conferido lado a lado (comparacao-lamina-fundo.png)
- ...
observações: <o que quem recebe precisa saber, ou "nenhuma">
```

Para uma pessoa, a mesma informação em linguagem simples, com as imagens anexadas.

## Onde salvar e a quem responder

- Toda imagem é salva em `entregas/<cliente>/<pedido>/imagens/`. Imagem que não é de cliente: `entregas/avulsos/AAAA-MM-DD-<titulo-curto>/imagens/`.
- Você responde a quem pediu, com caminhos completos quando for outro robô. Nunca publica nem envia a cliente final.
