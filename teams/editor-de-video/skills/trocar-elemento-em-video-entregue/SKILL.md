---
name: trocar-elemento-em-video-entregue
description: "Trocar uma imagem, objeto, produto ou menção em um vídeo de motion já entregue sem renderizar tudo de novo: localizar o elemento na configuração da cena, buscar a imagem substituta de fonte oficial ou licenciada, recortar o fundo com borda suavizada, ajustar ao tamanho original, atualizar só a cena afetada, remontar o vídeo e conferir áudio e quadros. Inclui troca de produto ou serviço citado, com nova gravação de voz. Use quando pedirem para trocar, substituir ou refazer só a cena de um elemento num vídeo pronto."
---

# Trocar um elemento em vídeo entregue

O vídeo já foi entregue e aprovado; só um ou dois elementos mudam. Troque de forma eficiente, sem renderizar o vídeo inteiro.

## Quando usar

A pessoa diz "troca a imagem do X", "coloca a foto do Y", "substitui esse elemento", "refaz só a cena da imagem do Z" ou aponta um quadro e pede para trocar algo. Também em troca de produto ou serviço citado ("troca o produto A pelo produto B"), que pode incluir regravar a voz.

## Procedimento

1. **Localize o elemento na configuração do projeto.** Ache o arquivo de cena que o contém (procure o nome do arquivo ou do elemento nos arquivos de cena) e leia a configuração inteira: posição, escala, camada e tempo. Em troca de produto, ache todas as cenas que citam o nome ou mostram preço e detalhes.
2. **Consiga o substituto.**
   - **Imagem (retrato, objeto):** se for pessoa real, prefira fontes oficiais ou de domínio público (retratos oficiais de órgãos públicos). Busque pela API da Wikimedia Commons (`https://commons.wikimedia.org/w/api.php?action=query&list=search&srsearch=...`) e baixe da página oficial do arquivo. Sem fonte de domínio público, confirme com a pessoa antes de usar qualquer outra.
   - **Produto ou serviço citado:** grave a nova narração com a mesma voz e as mesmas configurações da original (ElevenLabs) e extraia o tempo de cada palavra em JSON `[{p: palavra, i: início_ms, f: fim_ms}]`. Atualize os textos na tela (nome, preço, descrição) na configuração.
3. **Processe o substituto.**
   - **Imagem:** remova o fundo (`rembg i -m isnetgen4 entrada.jpg saida.png`; se o recorte sujar, tente outro modelo, por exemplo `-m isnet-anime` para ilustração). Redimensione para o tamanho do original, que você mede na configuração da cena ou na folha de conferência do render antigo. **Suavize a borda** (obrigatório): com Pillow, aplique um degradê de alfa de 1 para 0 em 10 a 15 pixels no contorno, para a emenda sumir contra o fundo. Recorte de borda dura aparece na hora.
   - **Voz:** extraia o tempo do novo arquivo e compare a duração com a original para saber se contadores, animações ou textos precisam de ajuste.
4. **Copie para os arquivos do projeto.** Salve a imagem processada na mesma pasta da original, com nome semântico (`rosto_fulano`, não `img_nova_01.png`). Voz vai para a pasta de áudio do projeto com o nome no padrão dos outros.
5. **Atualize a configuração da cena.** Troque a referência ao arquivo; em troca de produto, atualize textos, nomes e preços em todas as cenas afetadas. Se o tempo da nova voz pede ajuste (um contador que chega ao valor em outro momento), ajuste os tempos às novas palavras. Deixe posição, escala e estrutura como estavam, salvo o que o conteúdo novo exigir.
6. **Renderize só a cena afetada**, com o script de render de cena do projeto. Não renderize o vídeo inteiro. Se estiver renderizando mais de uma cena, pare e confira se a troca realmente toca várias cenas. Extraia quadros a cada 0,5 s para conferir tamanho, mistura e posição.
7. **Remonte o vídeo** com o script de montagem do projeto, apontando para a(s) cena(s) nova(s). A montagem junta os clipes; não renderiza nem remixa o áudio. Mantenha o padrão de nome de entrega (próxima versão).
8. **Confira e entregue.** Veja a fronteira onde a cena começa: sem artefato, sem desalinhamento. Troca só de imagem: o áudio fica intocado (mesmo loudness, mesmos efeitos nos mesmos tempos; ouça a emenda). Troca com voz nova: a voz está audível, no nível certo e sincronizada com o texto. Entregue com "Segue com a imagem trocada. Aprova ou quer ajuste?" (ou "Segue com <produto novo> no lugar de <anterior>. Aprova ou quer ajuste?") e o arquivo anexado.

## Cuidados

- **Não renderize o vídeo inteiro.** Só a cena que mudou; a montagem leva segundos.
- **Borda suavizada não é opcional.** Num fundo com degradê, retícula ou textura, o recorte duro vira defeito. Confira ampliando a borda num quadro.
- **O tamanho tem que bater com o original.** Substituto visivelmente maior ou menor parece errado mesmo bem recortado. Meça o original primeiro.
- **Licença é sua responsabilidade.** Imagem de pessoa real exige permissão ou domínio público (retrato oficial de órgão público, Creative Commons com a licença certa). Na dúvida, pergunte.
- **Ajuste de tempo para caber o conteúdo novo é aceito.** Se a pessoa quer o elemento em outro momento ou muda a estrutura da cena, isso é reedição: siga o método completo de `direcao-e-edicao-de-video`.
- **Troca de voz exige conferir a mistura.** A nova narração fica no mesmo nível, com os mesmos efeitos e trilha da cena original. Se a original não tinha música naquele trecho, não acrescente.

## Antes de entregar

Os quadros mostram o substituto no lugar certo e no tamanho do original, com borda lisa e sem halo. O áudio passa limpo pela emenda. A duração só mudou se o conteúdo novo exigiu. Em troca com voz, a nova voz está audível e sincronizada. Você assistiu ao trecho afetado no arquivo de entrega.
