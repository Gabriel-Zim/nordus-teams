---
name: estrategia-de-conteudo-para-redes
description: "Método do estrategista de conteúdo para qualquer pedido de ideia, pauta, calendário ou peça para redes sociais (reel, carrossel, estático, legenda, thread): ler a ficha da marca, definir objetivo e tese, pesquisar a conta e o nicho com fonte e data, escrever três hooks realmente diferentes, entregar numa mensagem curta com um documento anexado (topo, índice, preciso saber, aprovação em texto), aplicar o humanizador de copy e conferir a revisão final contra as regras da marca. Use em todo pedido de conteúdo para redes."
---

# Estratégia de conteúdo para redes

Siga as etapas na ordem. As regras de pensamento, entrega, escrita e verdade estão na sua alma; aqui está o procedimento.

## 1. Ficha da marca

Cada marca tem a sua ficha em `marcas/<marca>/ficha.md`: o que a marca é e o que não é, público, voz e vocabulário (o que usar e o que evitar), pilares, idioma de publicação, formatos que funcionam e seus limites (por exemplo, número máximo de slides), horário de publicação, assinatura, regras de compliance e o que está em aberto. Leia só a ficha da marca do pedido; nunca a de outra.

- Sem ficha: monte a versão 1 do plano com todas as suposições marcadas [hipótese] (posicionamento proposto, pilares, calendário, pautas com hooks) e, no fim, até 3 perguntas para a pessoa validar. Grave a ficha com o que for confirmado.
- Ficha que muda por pedido da pessoa: atualize a ficha e registre em `aprendizados.md`.

## 2. Objetivo e pesquisa

1. Diga em uma linha o objetivo real (alcance, salvamento, lead, autoridade, venda) e como vai medir.
2. Leia os últimos 30 posts da conta e de 3 a 5 peças comparáveis antes de escrever. **Outlier** é a peça com visualizações acima de 3 vezes a mediana da conta; referências valem até cerca de 10 vezes o tamanho da conta. Priorize envios e salvamentos por alcance, retenção, conversão e qualidade de lead; visualizações brutas pesam pouco. Dados recentes da conta prevalecem sobre guias.
3. Pesquise na web o que está performando no nicho agora, notícias com data e comentários do público. Cada fato leva fonte oficial e data. Dado frágil não entra na peça.
4. Pauta: parta dos pilares, da fila existente, do contexto atual e de 2 ou 3 hipóteses testáveis do `aprendizados.md`, com horário e justificativa verificável por pauta.

## 3. Tese e hooks

Toda ideia nasce de uma tese específica. Para cada peça, escreva três hooks realmente diferentes (racional, emocional, de curiosidade), escolha e defenda **um** recomendado e diga em uma linha por que deve funcionar. As alternativas entram em uma linha cada, só se forem realmente diferentes. O hook e a prova visual vêm antes da marca: educa antes de vender.

## 4. Formatos de entrega

**Pauta:** `# Pauta | MARCA | semana`. Fila e fonte; hipóteses H1 a H3; horário; por ideia numerada: formato, pilar, título interno, 3 hooks, estrutura, rede, por que agora (fato, data, link), chamada, executor, hipótese testada, compliance. Status: aprovar, negar ou ajustar.

**Roteiro de reel:** `# Roteiro | MARCA | título | duração`. 3 hooks; texto na tela; sequência com timecode, fala, tela e B-roll; prova visual até 5 s; reviravolta; chamada curta; 3 frases de capa; editor a confirmar. Números por extenso para voz sintética.

**Carrossel:** `# Carrossel | MARCA | título | N slides`. Objetivo e pilar; slide 1 capa com hook; cada slide com título, apoio e destaque; fechamento; legenda. Respeite o limite de slides da ficha. Todos os slides vão no documento, do primeiro ao último.

**Legenda:** linha 1 hook independente (ou a chamada primeiro, se a ficha pedir); 2 a 4 parágrafos curtos sem repetir o vídeo ou os slides; chamada única; hashtags relevantes.

## 5. Como apresentar na conversa

Resposta de estratégia, uma mensagem só, nesta ordem:

1. **Topo, 3 linhas:** Objetivo. Tese. Material usado (ou "sem material ainda").
2. **Índice, uma linha por ideia:** "Ideia 1 | Reel 45 s | alcance + lead | 7 de 9 cenas com material".
3. **Cada ideia no chat:** só título e hook, numa linha. O resto está no documento.
4. **Preciso saber:** as faltas e dúvidas numeradas com opções por letra, para responder rápido. Exemplo: "6. Antes e depois da obra: (a) já tem foto, (b) buscar na internet, (c) gerar com IA, (d) gravar na próxima visita".
5. **Aprovação em texto:** "Responda: aprovo 1 | ajusta 2: ... | 6c". Nunca cartão.
6. **Uma linha final** com avisos operacionais, se houver.

Anexe **um único documento** (Markdown ou HTML) com o entregável inteiro, no qual a pessoa vê, edita e comenta: slides completos, legenda final, roteiro falado completo, hooks, links e a lista "Validar antes de postar". Em peça publicada em outro idioma, cada texto leva a tradução em português ao lado (campos `_pt`): fiel e natural, só para leitura da pessoa, nunca na copy final. Um arquivo `.md` extra é cópia de segurança, nunca substituto. No chat, a mensagem fica curta: topo, uma linha por ideia, "Abra o documento e me diga por número o que aprova".

## 6. Revisão da pessoa

Quando a pessoa devolver aprovações e ajustes em texto:

1. Marque as aprovadas como validadas (grave em `marcas/<marca>/ideias-validadas/`). O que foi aprovado sem ressalva não se mexe.
2. Ajuste só o que ela pediu e gere o documento revisado. Se ela mudou o português de uma peça em outro idioma, reescreva o texto original na voz da marca a partir do português novo e peça que confirme o par; só então a ideia vira validada. Se ela mudou o texto original, refaça a tradução.
3. Responda curto: o que ficou validado, o que espera confirmação, o que você ajustou (uma linha cada) e "Confere o documento final e me diga se está certo". Anexe o documento revisado. Nada de repetir a peça no chat.
4. Depois do "aprovo": gere a decupagem final para a edição (`ideia-N-decupagem.md`: arquivo, timecode de entrada e saída, link, texto de tela, fala, o que falta e quem resolve) e entregue à pessoa. Falta material de internet: registre fonte e licença. Geração paga (imagem, vídeo) só com cotação e o "sim" da pessoa.

## 7. Humanizar e conferir

1. Toda copy final passa pelo humanizador de copy do time antes de ir à pessoa (alma). Confira se algum fato mudou.
2. **Revisão final obrigatória:** releia a entrega contra as regras duras da ficha da marca, uma por uma, e corrija. Fala e texto de tela sem nenhuma lacuna entre colchetes (escreva com o que você sabe; o que depende do cliente vai para "Validar antes de postar").
3. **Checklist:** o documento está anexado como único anexo? O chat está curto (topo, uma linha por ideia, preciso saber, aprovação), sem repetir slides nem legenda? Copy limpa, sem colchetes? Objetivo claro? Tese específica? Pesquisa com fonte e data? Hooks realmente diferentes? Porquê de cada escolha? Marca, idioma, voz, formato, horário e chamada certos? Sem número inventado, nome interno, travessão, emoji ou clichê? Compliance da marca? Copy final passou pelo humanizador?
