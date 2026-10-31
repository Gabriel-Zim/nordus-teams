# EDITOR DE VÍDEO

Edita e dirige vídeo do bruto ao arquivo final: edit falando, tela dividida, motion, cenas de IA, voz, trilha e mixagem, com conferência quadro a quadro.

## O que ele faz

Um editor e diretor de vídeo que faz o departamento inteiro sozinho. Estuda o bruto e as referências quadro a quadro, decupa o vídeo, escolhe a ferramenta certa para cada cena (ffmpeg, motion por código, 3D, cenas de IA, voz sintética, avatar, trilha licenciada), roda o que é independente em paralelo, testa com quadros soltos antes do render pesado, mede o áudio e a imagem, olha os quadros e refaz o que ficou feio antes de anexar o vídeo na conversa. Cota qualquer geração paga e só gasta com o seu ok.

## O que você recebe

- Reels, Shorts e vídeos de motion entregues em alta, com legenda, letreiros, trilha e efeitos no lugar certo.
- Cada vídeo estudado contra a referência e conferido em quadros e em áudio (-14 LUFS) antes de chegar até você.
- Ajustes por minutagem viram versão nova, sem refazer o que já estava aprovado.

## Quem está no time

| Bot | Título | O que faz |
|---|---|---|
| EDITOR DE VÍDEO | Editor de vídeo (edit falando, motion e cenas de IA) | Edita e dirige vídeo do bruto ao arquivo final: edit falando, tela dividida, motion, cenas de IA, voz, trilha e mixagem, sempre conferido quadro a quadro. |

## Antes de usar

Tempo para configurar: cerca de 15 minutos.

- **Tela do bot com ffmpeg** (obrigatória): cortar, reenquadrar, mixar, exportar e medir o vídeo.
  Como: instale o ffmpeg na máquina em que o robô roda (no Mac, brew install ffmpeg) ou ligue ao robô, na Tela do bot, uma máquina que o tenha.
- **Zim Studio** (opcional): criar cenas de IA, B-roll gerado, troca de rosto e outros ângulos.
  Como: em Apps conectados, aba Conexões avançadas, ligue a conexão zim-studio (https://mcp.zim.studio/mcp) e preencha o valor Authorization com a chave da sua conta.
- **ElevenLabs** (opcional): voz sintética, locução e efeitos sonoros novos.
  Como: em Apps conectados, aba Conexões avançadas, ligue a conexão elevenlabs (https://api.elevenlabs.io/v1/mcp) e preencha o valor xi-api-key com a chave da sua conta.
- **HeyGen** (opcional): vídeos com avatar.
  Como: em Apps conectados, aba Conexões avançadas, ligue a conexão heygen (https://mcp.heygen.com/mcp/v1/) e entre com a sua conta.
- **Epidemic Sound** (opcional): trilha e efeitos sonoros licenciados.
  Como: em Apps conectados, aba Conexões avançadas, ligue o servidor MCP do Epidemic Sound com o endereço e a chave que a Epidemic Sound informa para a sua conta.

## Conexões incluídas

Elas chegam **desligadas**. Abra Apps conectados, aba Conexões avançadas, ligue a conexão e preencha o valor pedido. O valor nunca viaja no modelo.

| Conexão | Endereço | Valor que você preenche |
|---|---|---|
| Zim Studio | https://mcp.zim.studio/mcp | Authorization |
| ElevenLabs | https://api.elevenlabs.io/v1/mcp | xi-api-key |
| HeyGen | https://mcp.heygen.com/mcp/v1/ | nenhum (a entrada é pela sua conta) |

## Habilidades incluídas

Elas chegam **desligadas**. Revise e ligue cada uma no perfil do bot.

- `direcao-e-edicao-de-video`: Método de diretor e editor de vídeo para todo pedido de vídeo (edit falando, tela dividida, motion, filme com cena de IA, cortes de vídeo longo): abrir a pasta do pedido, estudar o bruto e as referências quadro a quadro…
- `estudar-referencia-de-video`: Baixar e analisar um vídeo de referência quadro a quadro para copiar a técnica com precisão: folhas de contato com tempo, tiras de transição no fps nativo, transcrição com tempo, medição de loudness e quebra escrita em…
- `variacao-de-video-aprovado`: Criar uma V2 ou variação de um vídeo já aprovado sem mexer no original: separar as mudanças pedidas, apresentar amostras de voz antes de gerar, confirmar as especificações por escrito, copiar a receita para uma pasta no…
- `trocar-elemento-em-video-entregue`: Trocar uma imagem, objeto, produto ou menção em um vídeo de motion já entregue sem renderizar tudo de novo: localizar o elemento na configuração da cena, buscar a imagem substituta de fonte oficial ou licenciada, recort…
- `motion-com-narracao-profissional`: Produzir vídeo de motion para uma marca com narração de locutor (voz da biblioteca da ElevenLabs ou voz própria já aprovada), assets gerados ou oficiais, tipografia cinética, câmera viva, trilha e efeitos licenciados da…
- `animacao-explicativa`: Vídeo vertical que explica qualquer assunto sem ninguém gravar: roteiro em estrutura fixa (gancho comparativo, jeito comum, reviravolta, mecanismo em 3 ou 4 telas, metáfora, pergunta final), narração gravada uma vez com…
- `video-com-avatar-e-voz-sintetica`: Vídeo em que a pessoa não grava: roteiro curto, voz sintética da ElevenLabs, avatar no HeyGen, material real do assunto, motion em cima e avatar embaixo, legenda, trilha licenciada e entrega. Inclui a regra de aprovação…

## Como instalar

1. Abra **Modelos**, na barra lateral do Nordus, escolha este modelo e carregue. Ou importe o arquivo `editor-de-video.nordusteam.json`. Você vê uma prévia antes de qualquer coisa ser adicionada.
2. Ligue as habilidades de cada bot.
3. Siga o **Antes de usar** acima.
4. Depois de conectar um app em **Apps conectados**, ligue a chave **Apps conectados** do bot em **Configurações → Acesso**. Sem isso o bot não enxerga o app.
5. Rotinas não vêm incluídas. Peça ao bot as automações de que você precisa.

## Autoria e licença

Autor: Nordus. Licença: Apache-2.0.
