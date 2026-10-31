---
name: fluxo-de-conteudo-social-media
description: "Leva o conteúdo de uma marca da pauta ao post: separar o pedido em partes (pauta, ideia e copy, vídeo, design, capa de reel, pesquisa, artigo, legenda), mandar cada parte a quem faz por coordinate_bots com o briefing inteiro, mostrar a fala e a peça à pessoa e esperar o ok antes de seguir, e só publicar ou agendar quando ela mandar. Use em qualquer pedido de conteúdo: 'faz um conteúdo', 'monta um reel', 'escreve a copy', 'faz a capa', 'traz pautas', 'revisa a legenda', 'posta', 'agenda'."
---

# Fluxo de conteúdo: da pauta ao post

Quando a pessoa pedir um conteúdo, cada parte vai para quem faz aquilo. A aprovação fica nesta conversa. Publique ou agende só quando ela disser para postar, agendar ou publicar. Não peça para ela abrir a conversa de outro bot.

## Quando usar

- "faz um conteúdo", "monta um reel", "escreve a copy", "faz a capa", "pesquisa isso"
- "tem pauta", "traz pautas", "ideia de reels"
- "revisa a copy", "manda a legenda", "posta agora", "agenda", "posta e faz a capa"
- Qualquer peça nova de ideia, copy, vídeo, design ou pesquisa da marca

## Procedimento

1. **Separe o pedido** em: pauta, ideia e copy, vídeo, design (incluindo capa de reel), pesquisa, artigo, legenda e automação. Leia a ficha da marca e só a dela.
2. **Pauta:** peça ao pesquisador do time (se houver) ou ao estrategista de conteúdo. Devolva cerca de seis ideias numeradas, com reel na frente, cada uma com um gancho que dê para mostrar na tela. Carrossel entra só se a pessoa pedir. Ela escolhe por número; o que for não, ou "deixa quieto", cai fora. Se o editor já estiver nesse item, mande parar. Se ela disser que são as mesmas notícias, traga fatos novos que dê para mostrar na tela; não reapresente a lista recusada com outro formato.
3. **Ideia e copy:** `coordinate_bots` para o estrategista de conteúdo, com o gancho e os fatos que não podem mudar. Mostre a fala nesta conversa e espere o ok antes de passar ao editor. Termos e frases que a pessoa ditar (acesso, site, plano, preço, abertura, ênfase, frase pessoal) entram literais. Se ela travar um texto, não peça reescrita por cima.
4. **Vídeo, reel, corte ou motion:** o mesmo para o editor de vídeo. Rascunho, sem publicar. A fala vai fechada, a versão que a pessoa já viu. Tela do computador mostrada no vídeo é animação de exemplo, sem arquivo real, a menos que ela peça para gravar (gravação expõe arquivo pessoal). Se ela quiser a tela provando como o produto funciona, peça os exemplos oficiais (página e vídeo) e cite as URLs no pedido.
5. **Design, estático, carrossel ou capa de reel:** o mesmo para o designer gráfico. A capa de reel entra junto, sem esperar o vídeo. Se a pessoa pedir a capa e postar no mesmo pedido, peça a capa agora e segure o post até o arquivo existir.
6. **Pesquisa, número e fonte:** o mesmo para o pesquisador. Cada número volta com o link. Não invente o que ele ainda não devolveu.
7. **Artigo:** se nascer de um reel, comece fiel à fala aprovada. "Mais detalhado" ou "como começar" expande o passo a passo (para quem é, o que entra, o que sai, qual ferramenta faz o quê, o que é proibido) sem trocar os números aproximados da fala. Mostre o texto aqui. Só publique no site quando ela mandar, e confirme que a URL abre.
8. **Um pedido por vez para cada bot, com o briefing inteiro.** Se já houver pedido em andamento, mude com outro `coordinate_bots` para o mesmo bot. Não reenvie o mesmo pedido. Para pedido de gravação ou materiais, reúna no briefing as instruções de captação, incluindo gravação de tela e material real quando solicitados. Se houver um identificador de tarefa e a pessoa pedir que ele conste no nome da pasta do pedido, use-o na pasta e no briefing.
9. **Quando a peça voltar,** mostre aqui, imagem ou vídeo na mensagem, e pergunte em texto se aprova ou quer ajuste. Se ela já mandou postar e a capa era desse pedido, mostre a capa e publique nesse turno, sem perguntar de novo.
10. **Depois do ok:** "posta agora" publica na hora; "agenda" segue a skill `aprovacao-e-agendamento-de-posts`.

## Cuidados

- Pedido parado num ok na conversa de outro bot não anda sozinho. Avise numa frase e não mande a pessoa procurar cartão.
- A copy que a pessoa escreveu vale por cima da versão do estrategista.
- Vídeo não vai para o designer. Capa não vai para o editor. Pesquisa não vira copy.
- Não mande a fala ao editor antes de mostrar aqui e receber o ok. O vídeo trava a frase e cada correção vira outro pedido.
- O nome do produto é o que a pessoa ditou, sempre. Na fala sintética, confira que a pronúncia sai certa.
- Pauta volta com reel na frente. Lista só de carrossel, ou a mesma notícia reescrita como vídeo, não é o que ela pediu para filmar.
- Notícia que a pessoa recusou para na hora, também no editor.
- Não publique o reel enquanto a capa pedida no mesmo pedido ainda está com o designer: o post que já saiu fica com um quadro do vídeo, porque a capa não entra depois.

## Antes de dar por terminado

A fala foi mostrada aqui e o ok veio antes do pedido ao editor. Cada parte pedida tem o recibo do `coordinate_bots` no bot certo. Post no ar ou na grade tem o link do calendário, a capa pedida já está nele e a frase de acesso está na legenda. Artigo publicado abre na URL do site. Para encaminhamento de pauta, o recibo confirma que o briefing completo chegou ao bot designado.
