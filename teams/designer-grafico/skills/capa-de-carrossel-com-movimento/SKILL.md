---
name: capa-de-carrossel-com-movimento
description: "Desenha a capa estática de um carrossel já pronta para animação (camadas isoladas e nomeadas, o resto travado) e entrega ao editor de vídeo com a especificação de movimento, tempo e ponto final do loop. Cobre a capa padrão com um ou dois elementos temáticos em movimento e a capa em estilo de notícia, com vídeo, tarja rolante e selo. Use quando pedirem capa animada ou mostrarem uma referência de capa com movimento."
---

# Capa de carrossel com movimento

Desenhe o quadro estático da capa com os elementos de animação isolados e passe ao editor de vídeo (o robô de edição do time, se houver, ou a pessoa que anima) com a especificação do movimento. A capa funciona mantendo quase todo o desenho travado, com só um ou dois elementos temáticos se movendo num loop curto.

## Quando usar

Quando a capa do carrossel precisa de movimento (pedido de "capa animada" ou uma referência de post animado), quando começa uma série cujas capas devem chamar atenção com movimento, ou quando a referência é uma capa em estilo de notícia, com vídeo e faixa rolante.

## Princípios de design

- **Híbrido estático e animado**: a maior parte do desenho fica travada (foto, texto, grade, cores) e só um ou dois elementos escolhidos se movem. Isso mantém a coesão de um design, não de um vídeo.
- **Escolha do elemento**: peça ligada ao tema do carrossel (um globo para tema global, um contador para tema de métrica). Evite movimento em fundo ou no texto principal.
- **Tempo do loop**: ciclos de 6 a 18 segundos no total, com o movimento repetindo de 2 a 3 vezes antes de a capa assentar no chamado ("Arraste para ver mais").

## Procedimento: capa animada padrão

1. **Desenhe o quadro da capa** no Figma, estático e completo, em 1080 x 1350, seguindo as regras da skill `carrossel-de-redes-sociais`.
2. **Escolha 1 ou 2 candidatos** à animação: elementos que reforçam o tema e se movem bem.
3. **Isole cada elemento animado em uma camada própria** com nome claro (`globo-animar`, `contador-animar`) para o editor extrair.
4. **Trave todas as outras camadas** (fundo, texto, foto, grade, selos).
5. **Prepare a especificação**: liste os elementos que se movem; descreva o movimento (girar, dissolver, contagem regressiva, explodir); sugira o tempo (duração total, ciclos, ponto de volta do loop); inclua o quadro do chamado em que o movimento termina.
6. **Exporte o quadro em PNG** (1080 x 1350) e envie ao editor de vídeo com a especificação e o link do Figma.
7. O editor produz a capa animada; você entrega o carrossel estático normalmente.

## Procedimento: capa animada em estilo de notícia (vídeo e tarja rolante)

Quando a referência é uma capa de notícia (vídeo do tema, faixa rolante por cima e título embaixo):

1. **Peça o vídeo da notícia** (vídeo real do fato ou do tema) a quem pesquisa, ou à pessoa.
2. **Desenhe o quadro de layout** no Figma (1080 x 1350) com:
   - espaço do vídeo (metade de cima, bordas seguras marcadas);
   - posição da tarja rolante (sobreposta, animada, por exemplo "URGENTE" ou um ticker);
   - selo ou etiqueta fixa (canto);
   - título e chamado (embaixo, fixos, em serifa forte mais sem serifa, com ponto de assentamento entre 6 e 8 segundos);
   - fundo preto ou escuro para enquadrar.
3. **Isole a tarja e o selo em camadas de animação** com nomes claros (`tarja-animar`, `selo-revelar`).
4. **Trave todo o resto** (fundo, título, espaço do vídeo, chamado).
5. **Prepare a especificação de entrega**: o arquivo de vídeo; o movimento da tarja (direção, duração, repetições, por exemplo "rola para a esquerda em 3 s, repete 2 vezes"); o tempo de entrada do selo (surgir, ficar parado ou deslizar com a tarja); a atribuição de fonte, com um pequeno "Fonte: nome do canal" no canto quando o vídeo vier de telejornal; o loop terminando no chamado entre 6 e 18 segundos.
6. **Envie ao editor**: vídeo, quadro do Figma e especificação (movimento da tarja, tempo do selo, ponto final do loop).
7. O editor produz a capa animada com vídeo e tarja rolante; você entrega o carrossel estático junto.

## Armadilhas

- **Animar elementos demais**: movimento dilui o desenho. Fique em 1 ou 2 elementos temáticos; o resto trava.
- **Sem especificação**: o editor precisa saber o que se move, como e por quanto tempo. Seja explícito (por exemplo "o globo gira 360 graus em 2 s, trincas aparecem em 1 s, explode aos 3 s; o loop repete 3 vezes e termina aos 18 s no chamado").
- **Texto principal em movimento**: texto em movimento é difícil de ler. Mantenha o título travado e anime os gráficos de apoio.
- **Esquecer o chamado no loop**: a capa precisa assentar em "Arraste para ver mais" ou no selo do tema, para a pessoa saber que deve deslizar.
- **Estilo notícia, espaço do vídeo impreciso**: marque a área do vídeo com guias e rotule ("Vídeo 1080 x 675 aqui") com dimensões e bordas seguras.
- **Estilo notícia, tarja rápida demais**: faixas rolantes leem bem entre 3 e 5 segundos por rolagem completa. Mais rápido borra, mais devagar perde o interesse. Combine o tempo com o editor antes do final.

## Verificação

- O desenho da capa está completo e estático (1080 x 1350).
- Os candidatos à animação estão isolados em camadas com nomes claros.
- Todas as outras camadas estão travadas.
- A especificação traz elementos, movimento, tempo e ponto final do loop.
- O PNG do quadro, o link do Figma e a especificação foram enviados ao editor de vídeo.
- O tempo típico foi respeitado (6 a 18 s, 2 a 3 ciclos).
- Para capa em estilo de notícia: o vídeo foi conseguido, o espaço dele está marcado, a tarja e o selo estão isolados, o movimento da tarja está explícito e a fonte do vídeo consta na especificação.
