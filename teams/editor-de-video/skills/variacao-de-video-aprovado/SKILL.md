---
name: variacao-de-video-aprovado
description: "Criar uma V2 ou variação de um vídeo já aprovado sem mexer no original: separar as mudanças pedidas, apresentar amostras de voz antes de gerar, confirmar as especificações por escrito, copiar a receita para uma pasta nova, testar a parte visual com quadros soltos e vídeos parciais, e só então gerar o vídeo completo. Use quando pedirem uma V2, uma segunda versão, uma versão mais polida ou outro igual mas com uma mudança."
---

# Variação de um vídeo aprovado (V2)

A variação é uma receita nova, em paralelo à original. A original continua intacta. Use pontos de aprovação, principalmente a voz, antes de gastar crédito com a geração completa.

## Quando usar

A pessoa diz "vamos fazer uma V2", "uma versão mais polida", "faz outro igual, mas com <mudança>" ou pede melhorias específicas num vídeo já aprovado.

## Procedimento

1. **Separe as mudanças em categorias:** voz, visual (local, avatar, fundo), tipografia, efeitos de áudio, ritmo, especificações técnicas.
2. **Mudança de voz: mostre opções antes.** Gere de 3 a 4 amostras do mesmo trecho (a frase mais curta que represente o vídeo). Descreva cada uma (tom, naturalidade, caráter: "conversada, sem processamento" ou "executiva, formal") e anexe todos os áudios numa única mensagem, porque anexos em mensagens separadas podem não chegar. Espere a escolha da voz antes de gerar o vídeo completo.
3. **Confirme por escrito** todo o resto (local, avatar ou fundo, tipografia, efeitos, resolução) antes de começar.
4. **Pasta nova** com sufixo `-v2` ou `-variacao`. Copie a original como molde e aplique as mudanças aprovadas. Não altere a pasta original.
5. **Mudança visual (tipografia, fontes, estilo, layout de texto): quadros de teste antes.** Renderize um pequeno conjunto de quadros e confira: o texto quebra sem cortar, a fonte carrega, espaçamento e tamanho batem. Compare com a original. Se algo falhar, corrija a origem e gere os quadros de novo.
6. **Variação em várias partes: renderize cada parte como vídeo completo antes da montagem final.** Se a variação mistura elementos complexos (animações de outra receita, transições de tela dividida, trechos compostos), renderize cada trecho separado para checar duração, qualidade e encaixe. Isso pega erro de tempo e sincronia que quadro solto não mostra.
7. **Gere o vídeo completo** só depois de voz aprovada, especificações travadas e a parte visual testada.
8. **Registre a receita nova** separada. Original e variação ficam no histórico do projeto.

## Cuidados

- A voz muda o ritmo do vídeo inteiro. Peça a aprovação da voz mesmo que todo o resto esteja pronto. Não gaste crédito na geração completa enquanto espera. Pare no passo da voz, nunca siga por suposição.
- **Áudio cortado ou sílaba comida num vídeo já gerado:** primeiro veja se a palavra aparece mais de uma vez no bruto; se aparecer, use outra tomada em que ela esteja limpa. Se todas estiverem cortadas ou a palavra aparecer uma vez só, o problema costuma estar na montagem: cortes feitos pelo tempo que a transcrição marca (fim da palavra) fecham cedo e comem a sílaba final. Refaça o corte por silêncio da forma de onda. Depois teste variações do processamento de voz (velocidade, estabilidade, tom). Registre qual tomada usou ("segunda ocorrência da frase").
- **Voz rejeitada no vídeo completo ("não ficou boa"):** não continue ajustando a mesma voz. Ofereça amostras novas com outras vozes e personalidades, variando tom e caráter (grave de narrador, conversada madura, natural solta), para a pessoa escolher o perfil que serve ao projeto.
- **Tipografia e renderização só aparecem no render.** Sintaxe do nome da fonte (aspas na regra de CSS), espaçamento e quebra de texto não se veem lendo o código. Gere sempre quadros de teste quando a especificação visual mudar, confira que as fontes carregam (`Playfair Display`, sem aspas internas na regra), corrija e regere os quadros antes do render completo.

## Antes de entregar

Amostras de voz anexadas num lote único com descrições claras e a escolha aprovada pela pessoa. Pasta nova com sufixo, separada da original. Nenhuma geração começou antes da aprovação da voz e da confirmação escrita das especificações. Mudança visual passou por quadros de teste vistos. Variação em partes teve cada trecho renderizado e conferido antes da montagem final.
