---
name: apuracao-de-fala-ou-numero-lembrado
description: "Conferir uma notícia, um número ou uma fala que a pessoa lembra e devolver quem publicou, quando, em que cenário e o que saiu depois, separando a projeção da instituição, o consenso e a fala pessoal, sem ajustar prazo ou cenário para o número lembrado caber. Use quando pedirem 'relembra essa notícia', 'de onde saiu esse número', 'alguém falou que...' ou 'o que fulano falou sobre isso'."
---

# Apuração de fala ou número lembrado

Confere um número, uma projeção ou uma frase que a pessoa lembra e devolve: quem publicou, o que a fonte disse, em que data e cenário, e o que saiu depois. Não desenha carrossel, não manda copy a outro bot e não substitui o relatório longo de `pesquisa-com-fonte`. As ideias de peça saem de `pauta-de-conteudo-com-fonte`.

## Quando usar

- "Relembra essa notícia", "me traz essa notícia de novo", "pesquisa notícias novas sobre isso".
- A pessoa cita de memória um número (cotação, meta, prazo) e pede para achar a matéria.
- "Alguém falou", "vi alguém falando esse número", "de onde saiu", mesmo sem nomear o autor.
- A pessoa nomeia uma instituição, mas o número pode ser de outra casa ou de um post.
- A pessoa corrige o autor depois de uma primeira resposta ("foi o fulano", "da casa X").
- "O que fulano falou", "a opinião dele".

## Procedimento

1. **Feche o pedido numa linha:** o número lembrado, o prazo, o mecanismo (se a pessoa deu um), o acontecimento que precisa entrar na atualização e quem falou (ou que a pessoa não nomeou o autor). Se ela corrigir o autor, o nome novo é o alvo; a fala achada antes só entra se for outra citação do mesmo número.
2. **Avise a etapa** com `informar_etapa`. Busque na web a frase lembrada (número, prazo, mecanismo e quem falou) e, na mesma passada, o que a instituição nomeada disse no ciclo mais recente. Abra as matérias que citam a instituição ou a pessoa. Se o sobrenome pode ter outra grafia, busque as duas e responda com a grafia publicada. Se a pessoa não nomeou o autor, ou a frase não aparece nessa instituição, busque o mesmo número e prazo na rede social onde ele circula. Se o autor nomeado publicou na própria conta, abra o post e o site da pessoa. Busca e matéria não trazem o texto inteiro do post, a hora nem o que o site diz sobre quem a pessoa é.
3. **Frase que não aparece na instituição nomeada:** abra dizendo que não achou nela e qual número ela publicou, com data e cenário. Não mude prazo nem cenário para o número lembrado caber. Em seguida nomeie quem publicou o número lembrado: pessoa ou casa, data, link, e que não é a instituição. Se a mesma conta já escreveu esse número antes, traga o post anterior com data e link. Se a pessoa nomeou outro autor depois, esse autor abre a resposta; o primeiro achado vem depois, como outra fala.
4. **Cargo, formação ou vínculo** que só aparecem no site da própria pessoa entram como "o que essa página afirma", até abrir a página da campanha, da casa ou do empregador. Se o post pede para chamar no direct, comprar ou contratar, o chamado entra na mesma frase que o número.
5. **Separe** a projeção da instituição, o consenso (mediana de economistas, por exemplo) e a fala pessoal ou de outra casa. Diga até quando a coleta foi, quando ela fecha antes do acontecimento. Use o mecanismo lembrado para casar a fala: número igual com mecanismo diferente é outra citação. Se a citação tem o número e não tem o ano lembrado, escreva o tempo que a própria frase marca. Se a mesma pessoa repetiu o mecanismo depois sem o número, diga que o número não voltou. Se não houver fala nova depois do acontecimento, diga isso: a entrevista antiga não é reação a ele.
6. **Monte uma tabela curta.** Caminho de uma instituição: uma linha por vez que ela falou (data, número, cenário). Vários autores para o mesmo número: uma linha por autor (quem, data, número, cenário). A mesma pessoa em datas diferentes ganha uma linha por fala; não copie o ano de uma fala para a outra. Não funda cenário-base e cenário de estresse. Um texto com um número por ano ganha uma linha por ano, não só o ano do pico.
7. **Duas redações divergem no mesmo dado:** mostre os dois valores e diga que não batem. Não faça média e não escolha um em silêncio. Se a manchete ou o título de um clipe traz um número e a página é fechada, e a transcrição aberta não traz a frase, cite só o que o trecho aberto diz; o número da manchete fica por confirmar.
8. **Responda em prosa curta, em português, nesta ordem:** correção (quem falou o número e quem não falou), o que mudou por último, contexto, tabela, links abertos. Se a pessoa corrigiu o autor, a correção abre por esse autor e pela citação publicada. Guarde o mesmo texto num arquivo e anexe.
9. **Pare na apuração.** Se no mesmo pedido pedirem ideias de conteúdo, siga `pauta-de-conteudo-com-fonte` com esta apuração já fechada. Se pedirem envio a outro bot, siga `encaminhamento-de-pedido-a-outro-bot`.

## Cuidados

- **Não confirme o número lembrado** quando a busca não acha a frase na fonte, e não cole o ano lembrado numa citação que não marca esse ano.
- **Não reduza um texto com um número por ano ao ano do pico.**
- **Não encerre na negativa da instituição nomeada.** A pessoa lembra o número que circulou; sem o autor, o pedido volta.
- **Não encerre no primeiro perfil que usou o número** quando a pessoa nomeia outro autor.
- **Não passe post pessoal ou de outra casa como fala da instituição** nomeada primeiro.
- **Não atribua a mediana de um consenso à instituição citada.**
- **Não confirme cargo ou vínculo** que só está no site da própria pessoa.
- **Não cite o número e cale o pedido de compra ou contratação** que está no mesmo post.
- **Não junte cenário-base e cenário de estresse numa faixa só.**
- **Não abra relatório longo nem ideias de carrossel neste passo.** O pedido é a notícia e o que saiu depois.

## Antes de dar por terminado

A primeira frase diz se a notícia lembrada foi achada e, quando a pessoa corrigiu o autor, abre por esse autor com a grafia publicada e o link. Cada número da tabela tem data, cenário e URL de uma página que você abriu. Divergência entre redações aparece com os dois valores. O arquivo foi anexado.
