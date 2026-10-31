---
name: imagem-por-codigo
description: "Receitas de imagem que precisam de código e não de IA: estender uma foto real para outra proporção sem redesenhar o que já existe (quadro na proporção final, IA só na área vazia, original colada de volta com emenda suave), recolorir mapa, infográfico ou print do cliente por código (a IA troca letras), ajuste fino de cor sobre o arquivo e montagem de comparação lado a lado. Use quando o pedido pedir outra proporção, recolorir uma imagem informativa ou provar que a foto real foi preservada."
---

# Imagem por código

Complementa a skill `geracao-de-imagem-com-ia`. Regra de ouro: o que é informação ou foto real do cliente é tratado por código; a IA só entra onde não existe nada a preservar.

## Estender para a proporção

Nunca peça à IA para estender a foto inteira: ela redesenha jardim, inventa degraus, move o objeto.

1. Monte por código o quadro na proporção final com a original encaixada na posição final, sem mudar a original.
2. Edite com o Zim Studio, usando esse quadro como primeira imagem, pedindo para completar só a área vazia e manter a área da foto idêntica.
3. Cole a original de volta, sem alteração, por cima do resultado, na mesma posição, com emenda suave de cerca de 2% nas bordas:

```sh
uv run --with pillow python - "<resultado>" "<original>" <x> <y> "<saida>" <<'EOF'
import sys
from PIL import Image, ImageFilter
res, orig = Image.open(sys.argv[1]).convert("RGB"), Image.open(sys.argv[2]).convert("RGB")
x, y = int(sys.argv[3]), int(sys.argv[4])
b = max(2, int(min(orig.size) * 0.02))
m = Image.new("L", orig.size, 0)
m.paste(255, (b, b, orig.width - b, orig.height - b))
m = m.filter(ImageFilter.GaussianBlur(b / 2))
res.paste(orig, (x, y), m)
res.save(sys.argv[5])
EOF
```

As coordenadas e a escala são as do quadro do passo 1. Se o modelo devolveu em outra resolução, redimensione o resultado para o tamanho do quadro antes de colar.

## Mapa, infográfico ou print fora da paleta

Nunca por IA (ela troca letras). Recorte a base limpa, sem o texto, e recolora por código com as cores do cartão do cliente, por exemplo `ImageOps.colorize` do Pillow entre o hex escuro e o claro da marca. O texto que estava na imagem vira texto no layout: mande-o a quem monta a peça. Se o texto está no meio da base e não dá para recortar, avise quem pediu.

## Ajuste fino

Cor de um fio, faixa com degraus de cor e afins: por código, sobre o arquivo. Retoque geral por IA piora a textura.

## Comparação lado a lado (prova de que a foto real foi preservada)

Monte a original e a editada na mesma altura, uma ao lado da outra, e salve como `comparacao-<nome>.png` na pasta do pedido:

```sh
uv run --with pillow python -c 'import sys; from PIL import Image; a,b=[Image.open(p).convert("RGB") for p in sys.argv[1:3]]; b=b.resize((int(b.width*a.height/b.height),a.height)); c=Image.new("RGB",(a.width+b.width,a.height)); c.paste(a,(0,0)); c.paste(b,(a.width,0)); c.save(sys.argv[3])' "<original>" "<editada>" "<pasta do pedido>/imagens/comparacao-<nome>.png"
```

Olhe a comparação com atenção: posição, tamanho, arquitetura, materiais, cores, número da casa e canteiros. Qualquer diferença reprova a imagem.
