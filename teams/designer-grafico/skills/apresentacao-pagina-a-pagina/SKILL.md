---
name: apresentacao-pagina-a-pagina
description: "Atualiza uma apresentação de várias páginas no Figma para ficar igual a uma versão nova de referência (PDF, exportação ou link), página por página e com decisões transparentes: compara escopo, prepara os assets, trabalha numa cópia, exporta e compara cada página, faz checkpoints por seção, usa exportação em lote por id de quadro, mantém duas apresentações paralelas em sincronia e resolve mapas que precisam ser reais e didáticos. Use quando pedirem para remontar, alinhar, atualizar ou corrigir uma apresentação."
---

# Apresentação página a página

Atualize um arquivo de design antigo para ficar igual a uma versão nova de referência (PDF, exportação ou link), página por página, com as decisões à vista e o conteúdo original preservado. Complementa a skill `design-no-figma`.

## Quando usar

Quando pedirem para "remontar", "alinhar", "atualizar para ficar igual" ou "corrigir" uma apresentação; quando um arquivo editável antigo precisa ter layout, texto e assets renovados para bater com uma versão nova; quando duas versões da mesma peça (arquivo antigo do Figma e PDF novo) precisam ser comparadas.

## Procedimento

1. **Receba as duas versões**: o arquivo editável antigo (Figma ou outro) e a referência nova (PDF, link ou exportação).
2. **Compare o escopo**: conte as páginas de cada uma; identifique páginas adicionadas, removidas ou reordenadas; anote as mudanças grandes de texto, imagem e layout. Crie um log (`registro.md`) para acompanhar o andamento.
3. **Prepare os assets**: extraia as imagens da referência (captura, exportação do PDF), reúna os trechos de texto e anote detalhes de layout numa pasta de trabalho. Se alguma página tem mapa, leia "Mapas que precisam ser reais e claros" antes de buscar a imagem.
4. **Crie uma cópia de trabalho** (nova página, ramo ou arquivo). O original fica intacto.
5. **Trabalhe página por página**: leia a página de referência de perto (texto, imagens, layout, espaçamento); atualize a cópia (texto, imagens, layout); envie as imagens novas ao Figma se preciso; iguale posição e tipografia; exporte a página e compare visualmente com a referência.
6. **Checkpoint a cada seção ou lote**: pergunte se pode continuar ou liste as decisões tomadas e espere o ok. Com o ok, siga sem perguntar de novo até a próxima seção.
7. **Exportação final e revisão**: exporte todas as páginas, monte uma comparação em grade (referência e atualizada lado a lado) e anexe para aprovação. Liste o que foi decidido sem aprovação explícita (conteúdo removido, erro de digitação corrigido, ajuste de layout) e peça aceite.

## Mapas que precisam ser reais e claros

Quando a página tem um mapa que deve mostrar a geografia verdadeira (posição real de prédios e ruas) e ao mesmo tempo ser didático (regiões fáceis de entender, construções visíveis), não escolha entre foto de satélite pura e ilustração pura. Faça assim:

1. **Base geográfica**: baixe ou extraia uma foto de satélite real da área, com prédios e ruas nas posições corretas.
2. **Processamento ilustrativo no Zim Studio**: envie a foto e peça uma edição de imagem com um modelo de edição fotográfica, com um pedido como "processe esta imagem de satélite para clareza e ilustração didática: simplifique os limites das regiões, mantenha os prédios visíveis como textura, ajuste contraste e cor para as regiões se destacarem, preserve a geografia exata".
3. **Revise a saída**: o resultado fica realista (geografia autêntica, prédios visíveis) e didático (regiões simplificadas, hierarquia clara).
4. **Integre**: suba o resultado ao arquivo de design como base do mapa e sobreponha os rótulos de região e a cartografia.

Esse método híbrido é a primeira escolha para mapas que precisam de realismo e clareza, não um plano B. Comece por ele para não ficar alternando entre satélite carregado demais e ilustração que perde a precisão.

## Exportação em lote por id de quadro

Em apresentação do Figma com 20 páginas ou mais, use ids de quadro e código para escolher, exportar e trocar imagens com eficiência:

1. **Mapeie páginas para ids de quadro**: use o painel de quadros ou links de compartilhamento para obter o id de cada página. Monte o mapa (por exemplo, `pagina-19=<id do quadro> pagina-20=<id do quadro>`) e confira 2 ou 3 ids na interface do Figma.
2. **Envie as imagens novas** (se for trocar fotos): baixe as imagens reais localmente (do Drive ou de outra fonte) e envie em lote ao arquivo do Figma pela ferramenta de envio de imagens, registrando de imediato os identificadores devolvidos.
3. **Aplique as imagens aos quadros por código**: rode um trecho da Plugin API do Figma que localiza cada quadro pelo id e troca o preenchimento do espaço da imagem pela imagem nova, usando os identificadores guardados.
4. **Exporte uma página por vez**: crie um script de exportação que receba os pares `página=id` como argumentos e rode em segundo plano; cada página sai como PNG nas dimensões do quadro (por exemplo 1920 x 1080). Isso é de 5 a 10 vezes mais rápido que a exportação em massa pela interface e evita estouro de tempo.
5. **Gere a grade de comparação**: com `montage` do ImageMagick em geometria fixa (`montage *.png -tile 3x7 -geometry 600x400+6+6 saida.jpg`) ou com Python (Pillow), sempre com tamanhos iguais para que as diferenças apareçam.
6. **Atualize o log** (`registro.md`) com data, páginas modificadas e o que mudou (texto, imagem, ordem).

## Apresentações paralelas em sincronia

Quando duas apresentações compartilham algumas páginas e divergem em outras (por exemplo uma de 35 páginas e outra de 32):

1. **Mapeie os ids entre os arquivos**: liste os quadros de cada arquivo por código (id e nome de cada nó da página) e monte um mapa de quais se sobrepõem (mesmo conteúdo, mesma atualização) e quais são exclusivos. Salve em `mapa-de-quadros.json`.
2. **Defina o escopo da atualização**: para cada página que a pessoa quer mudar, veja no mapa se ela existe em um arquivo, nos dois ou só em um.
3. **Aplique em paralelo**: nas páginas compartilhadas, atualize um arquivo e leve a mesma mudança ao outro (ou aplique por script de ids nos dois). Anote no `registro.md` em qual arquivo está mexendo.
4. **Exporte e verifique**: exporte as mesmas páginas dos dois arquivos e compare lado a lado; as páginas compartilhadas devem bater, salvo diferença intencional (um selo de status diferente, por exemplo).
5. **Documente a divergência**: registre no `registro.md` quais páginas são exclusivas de cada arquivo e não foram atualizadas.
6. **Gere os dois PDFs** em paralelo e confira número de páginas e tamanho do arquivo.

## Armadilhas

- **Exportação em massa lenta ou falha**: com 20 páginas ou mais, nunca exporte tudo de uma vez pela interface. Use o script com mapa de ids, uma página por vez.
- **Ids desconhecidos**: confira 2 ou 3 ids na interface (clique direito no quadro, informações do elemento, ou o link de compartilhamento) e teste com um id antes de montar o mapa inteiro.
- **Não guardar os identificadores de envio**: salve-os num arquivo assim que forem devolvidos; perder os identificadores obriga a reenviar tudo.
- **Fonte renderizando errado**: instale as fontes que faltam na máquina onde o design roda e reinicie o aplicativo; teste uma página antes de seguir.
- **Apagar páginas antigas ou sem uso**: guarde-as numa seção separada, com nome claro ("Páginas antigas", "Fora da referência"). A pessoa pode querer rever depois.
- **Seguir sem aprovação clara**: pergunte antes de remover conteúdo relevante, corrigir erro de digitação ou mudar layout. Na dúvida, liste as decisões no resumo e peça aceite.
- **Pular a conferência visual**: exporte a página e compare com a referência antes de ir para a próxima.
- **Comparação ilegível**: use tamanhos iguais na grade para as diferenças saltarem aos olhos.
- **Esquecer de atualizar as duas apresentações**: se compartilham páginas, uma atualização num arquivo sem o outro cria divergência. Veja o mapa antes de mexer.
- **Cortar demais as fotos**: foto de imóvel, produto ou assunto precisa do contexto inteiro (prédio inteiro, ambiente inteiro). Ajuste enquadramento e escala para mostrar o assunto completo, principalmente em apresentação imobiliária ou de produto.

## Verificação

- O original ficou intacto e existe uma cópia de trabalho.
- O andamento foi registrado no `registro.md` (páginas concluídas, decisões).
- Cada página foi exportada e comparada com a referência.
- Todos os assets novos foram enviados e posicionados.
- As páginas antigas estão numa seção separada, não apagadas.
- O que foi removido ou alterado foi listado e aprovado.
- A grade comparativa final tem tamanhos consistentes.
- Todas as páginas batem com a referência em conteúdo, ordem e layout.
- As imagens mostram o assunto inteiro, não pedaços.
- Mapas que precisam de realismo e clareza usaram o método híbrido (satélite com processamento ilustrativo).
- (Figma) O mapa de ids foi conferido em 2 ou 3 quadros e o script de exportação foi testado em 1 ou 2 antes do lote.
- (Arquivos paralelos) As páginas compartilhadas foram atualizadas nos dois arquivos e comparadas lado a lado, e a divergência está documentada.
