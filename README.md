# Modelos de times da Nordus

Bots prontos para montar o seu time. Cada modelo traz bots com função, habilidades, os conectores que ele precisa e o passo a passo de como ligá-los. Nada vem com credenciais: as conexões chegam desligadas e você preenche o que cada uma pede.

## Como instalar um modelo

1. Abra **Modelos**, na barra lateral do Nordus, escolha o modelo e carregue. Ou importe o arquivo `.nordusteam.json` da pasta do modelo.
2. Você vê uma prévia antes de qualquer coisa ser adicionada.
3. Ligue as habilidades de cada bot (chegam desligadas) e siga o **Antes de usar** do modelo.
4. Depois de conectar um app em **Apps conectados**, ligue a chave **Apps conectados** do bot em **Configurações → Acesso**. Sem isso o bot não enxerga o app.

## Modelos

| Modelo | Categoria | Para que serve | Configuração |
|---|---|---|---|
| [ATENDIMENTO](teams/atendimento/README.md) | Atendimento | Atendimento ao cliente que responde o chat e o e-mail de suporte do seu produto, trata falhas e cuida do pós-venda, dentro de uma política que você aprova. | cerca de 20 min |
| [DESIGNER DE IA](teams/designer-de-ia/README.md) | Design | Cria imagens pelo Zim Studio: gera e melhora fotos, transforma render em foto real e prepara assets sem texto para a peça final. | cerca de 5 min |
| [DESIGNER GRÁFICO](teams/designer-grafico/README.md) | Design | Monta capas de reels, carrosséis, posts e apresentações no Figma com nível de agência e usa o Zim Studio só para assets. | cerca de 10 min |
| [EDITOR DE VÍDEO](teams/editor-de-video/README.md) | Vídeo | Edita e dirige vídeo do bruto ao arquivo final: edit falando, tela dividida, motion, cenas de IA, voz, trilha e mixagem, com conferência quadro a quadro. | cerca de 15 min |
| [ESTRATEGISTA DE CONTEÚDO](teams/estrategista-de-conteudo/README.md) | Marketing | Estrategista de conteúdo que pesquisa a conta e o nicho, defende uma tese por peça e entrega pautas, reels e carrosséis com hooks fortes e copy humanizada. | cerca de 10 min |
| [FINANCEIRO](teams/financeiro/README.md) | Financeiro | Assistente financeiro que fecha as faturas mensais dos clientes, acompanha os alertas do banco, cobra atrasos e responde dúvidas, sem mexer no seu dinheiro. | cerca de 10 min |
| [GERENTE DE OPERAÇÃO](teams/gerente-de-operacao/README.md) | Operação | Gerente da operação que reparte cada pedido entre os bots do time, cobra prazos e pendências, faz o relatório diário e leva a você só o que depende de você. | cerca de 10 min |
| [PESQUISADOR](teams/pesquisador/README.md) | Pesquisa | Pesquisador que vasculha a web e os seus arquivos e volta com um brief: a resposta primeiro, a evidência com links e o que não deu para verificar. | cerca de 5 min |
| [PROGRAMADOR](teams/programador/README.md) | Desenvolvimento | Programador que altera, testa, commita e publica sites e plataformas, sempre pela última versão e só com o seu ok para ir ao ar. | cerca de 15 min |
| [PROJETISTA DE ROBÔS](teams/projetista-de-robos/README.md) | Automação | Projetista que desenha bots novos com você: função, instruções, habilidades, ferramentas, automações e riscos, em uma ficha pronta para criar no Nordus. | cerca de 5 min |
| [SOCIAL MEDIA](teams/social-media/README.md) | Marketing | Social media que planeja o conteúdo, pede design e vídeo ao time, leva tudo para a sua aprovação na conversa e só agenda o que você liberar. | cerca de 10 min |
| [TRÁFEGO PAGO](teams/trafego-pago/README.md) | Marketing | Time de nove bots que abre o projeto, testa criativos, opera a conta da Meta dentro de um teto e reporta o retorno, com revisão de política antes do ar. | cerca de 30 min |

### ATENDIMENTO

Atendimento ao cliente que responde o chat e o e-mail de suporte do seu produto, trata falhas e cuida do pós-venda, dentro de uma política que você aprova.

**Antes de usar:**

- **Caixa de e-mail de suporte** (obrigatória): ler e responder os e-mails dos clientes. Como: em Apps conectados, ligue o app do seu e-mail e entre com a conta do suporte (depois ligue a chave Apps conectados do bot em Configurações → Acesso); sem ele o atendimento não consegue atender por e-mail.
- **Chat do site** (opcional): responder as conversas do chat do seu site. Como: em Apps conectados, aba Conexões avançadas, ligue o servidor do seu chat ou sistema de atendimento, com o endereço e a chave que ele informa; sem ele o atendimento fala só por e-mail.
- **Sistema do seu produto** (opcional): consultar operações dos clientes e devolver crédito de operações que falharam. Como: em Apps conectados, aba Conexões avançadas, ligue o servidor MCP do seu produto (endereço e chave pelo seu painel de desenvolvedor); sem ele os casos de estorno vão para você.
- **Programador** (opcional): corrigir os defeitos da plataforma que os clientes relatam. Como: adicione ao mesmo workspace o modelo PROGRAMADOR, que está em Modelos, na barra lateral; sem ele o atendimento entrega as evidências e o patch a você.
- **Tela do bot** (opcional): guardar a política de atendimento, as respostas padrão e o registro. Como: ligue a Tela do bot; sem ela a política fica só na conversa.

[README do modelo](teams/atendimento/README.md)

### DESIGNER DE IA

Cria imagens pelo Zim Studio: gera e melhora fotos, transforma render em foto real e prepara assets sem texto para a peça final.

**Antes de usar:**

- **Zim Studio** (obrigatório): gerar, editar e melhorar imagens. Como: em Apps conectados, aba Conexões avançadas, ligue a conexão zim-studio (https://mcp.zim.studio/mcp) e preencha o valor Authorization com a chave da sua conta do Zim Studio.

[README do modelo](teams/designer-de-ia/README.md)

### DESIGNER GRÁFICO

Monta capas de reels, carrosséis, posts e apresentações no Figma com nível de agência e usa o Zim Studio só para assets.

**Antes de usar:**

- **Figma** (obrigatório): montar e exportar a arte no arquivo do cliente. Como: em Apps conectados, aba Conexões avançadas, ligue a conexão figma (https://mcp.figma.com/mcp) e entre com a sua conta do Figma; sem ela o bot explica o que falta e não improvisa.
- **Zim Studio** (opcional): melhorar fotos reais e gerar elementos ilustrados e fundos de contexto. Como: em Apps conectados, aba Conexões avançadas, ligue a conexão zim-studio (https://mcp.zim.studio/mcp) e preencha o valor Authorization com a chave da sua conta do Zim Studio.

[README do modelo](teams/designer-grafico/README.md)

### EDITOR DE VÍDEO

Edita e dirige vídeo do bruto ao arquivo final: edit falando, tela dividida, motion, cenas de IA, voz, trilha e mixagem, com conferência quadro a quadro.

**Antes de usar:**

- **Tela do bot com ffmpeg** (obrigatória): cortar, reenquadrar, mixar, exportar e medir o vídeo. Como: instale o ffmpeg na máquina em que o robô roda (no Mac, brew install ffmpeg) ou ligue ao robô, na Tela do bot, uma máquina que o tenha.
- **Zim Studio** (opcional): criar cenas de IA, B-roll gerado, troca de rosto e outros ângulos. Como: em Apps conectados, aba Conexões avançadas, ligue a conexão zim-studio (https://mcp.zim.studio/mcp) e preencha o valor Authorization com a chave da sua conta.
- **ElevenLabs** (opcional): voz sintética, locução e efeitos sonoros novos. Como: em Apps conectados, aba Conexões avançadas, ligue a conexão elevenlabs (https://api.elevenlabs.io/v1/mcp) e preencha o valor xi-api-key com a chave da sua conta.
- **HeyGen** (opcional): vídeos com avatar. Como: em Apps conectados, aba Conexões avançadas, ligue a conexão heygen (https://mcp.heygen.com/mcp/v1/) e entre com a sua conta.
- **Epidemic Sound** (opcional): trilha e efeitos sonoros licenciados. Como: em Apps conectados, aba Conexões avançadas, ligue o servidor MCP do Epidemic Sound com o endereço e a chave que a Epidemic Sound informa para a sua conta.

[README do modelo](teams/editor-de-video/README.md)

### ESTRATEGISTA DE CONTEÚDO

Estrategista de conteúdo que pesquisa a conta e o nicho, defende uma tese por peça e entrega pautas, reels e carrosséis com hooks fortes e copy humanizada.

**Antes de usar:**

- **Busca na web e navegador** (opcional): pesquisar a conta, o nicho e as fontes com data. Como: ative a busca na web e o navegador nas configurações do bot; sem eles o estrategista entrega só o que se sustenta e marca o resto como hipótese.
- **Métricas das redes sociais** (opcional): ler os últimos posts e as métricas da conta. Como: em Apps conectados, ligue o conector da ferramenta de métricas e agendamento que você usa (depois ligue a chave Apps conectados do bot em Configurações → Acesso), ou envie o relatório exportado; sem isso a métrica fica como não disponível.
- **Tela do bot** (opcional): guardar a ficha, o log e os aprendizados de cada marca. Como: ligue a Tela do bot; sem ela a estratégia sai na conversa e o histórico não fica guardado.
- **Designer gráfico e Editor de vídeo** (opcional): executar as peças aprovadas. Como: adicione ao seu workspace os modelos DESIGNER GRÁFICO e EDITOR DE VÍDEO, que estão em Modelos, na barra lateral.

[README do modelo](teams/estrategista-de-conteudo/README.md)

### FINANCEIRO

Assistente financeiro que fecha as faturas mensais dos clientes, acompanha os alertas do banco, cobra atrasos e responde dúvidas, sem mexer no seu dinheiro.

**Antes de usar:**

- **E-mail** (obrigatório): ler os alertas do banco e enviar faturas e cobranças depois do seu ok. Como: em Apps conectados, ligue o app da sua caixa de e-mail e entre com a sua conta (depois ligue a chave Apps conectados do bot em Configurações → Acesso); sem ele o financeiro trabalha só com o que você colar na conversa.
- **Tabela de clientes e contratos** (obrigatória): saber o valor, o vencimento, a forma de pagamento e o e-mail de cobrança de cada cliente. Como: conecte a planilha que você usa em Apps conectados, ou ligue a Tela do bot e coloque o arquivo financeiro/clientes.csv; sem a tabela o bot não fecha fatura e não inventa valores.
- **Plataforma de cobrança** (opcional): gerar link de pagamento, boleto ou Pix nas faturas. Como: em Apps conectados, ligue o app de pagamentos que você usa (depois ligue a chave Apps conectados do bot em Configurações → Acesso); sem ele a fatura leva os dados de pagamento que você informar.
- **Tela do bot** (opcional): guardar as faturas em PDF e o razão de entradas e saídas. Como: ligue a Tela do bot; sem ela o registro fica na conversa.

[README do modelo](teams/financeiro/README.md)

### GERENTE DE OPERAÇÃO

Gerente da operação que reparte cada pedido entre os bots do time, cobra prazos e pendências, faz o relatório diário e leva a você só o que depende de você.

**Antes de usar:**

- **Os outros bots do time** (opcional): receber os pedidos que o gerente reparte (design, vídeo, conteúdo, código, atendimento, dinheiro). Como: adicione ao mesmo workspace os modelos que a sua operação usa (todos estão em Modelos, na barra lateral); sem um deles o gerente diz qual falta e não improvisa o trabalho.
- **E-mail, agenda e arquivos em nuvem** (opcional): ler prazos, achar fatos no e-mail e abrir pastas compartilhadas. Como: em Apps conectados, ligue o app da sua caixa de e-mail, da sua agenda e do seu armazenamento em nuvem e entre com a sua conta (depois ligue a chave Apps conectados do bot em Configurações → Acesso).
- **Gerenciador de tarefas e agendador de redes sociais** (opcional): ver o que vence e o que está agendado para entrar no relatório da manhã. Como: em Apps conectados, ligue os apps que você usa (depois ligue a chave Apps conectados do bot em Configurações → Acesso); sem eles o relatório avisa o que não conseguiu ver.
- **Tela do bot** (opcional): guardar o quadro de status e as receitas do que já foi resolvido. Como: ligue a Tela do bot; sem ela o histórico fica só na conversa.

[README do modelo](teams/gerente-de-operacao/README.md)

### PESQUISADOR

Pesquisador que vasculha a web e os seus arquivos e volta com um brief: a resposta primeiro, a evidência com links e o que não deu para verificar.

**Antes de usar:**

- **Busca na web e navegador** (obrigatória): pesquisar, abrir as páginas e ler o que circula nas redes. Como: ative a busca na web e o navegador nas configurações do bot; sem eles o pesquisador só entrega o que se sustenta em fonte aberta e marca o resto como não verificado.
- **Arquivos em nuvem** (opcional): ler pastas e documentos que você compartilhar. Como: em Apps conectados, ligue o app de arquivos em nuvem que você usa e entre com a sua conta (depois ligue a chave Apps conectados do bot em Configurações → Acesso); sem ele, envie os arquivos na conversa.
- **Estrategista de conteúdo** (opcional): receber a ideia escolhida para escrever a copy. Como: adicione ao mesmo workspace o modelo ESTRATEGISTA DE CONTEÚDO, que está em Modelos, na barra lateral; sem ele o pesquisador para na lista de ideias.
- **Tela do bot** (opcional): guardar os briefs e as listas de fontes. Como: ligue a Tela do bot; sem ela o brief sai na conversa.

[README do modelo](teams/pesquisador/README.md)

### PROGRAMADOR

Programador que altera, testa, commita e publica sites e plataformas, sempre pela última versão e só com o seu ok para ir ao ar.

**Antes de usar:**

- **Tela do bot** (obrigatória): guardar o código, rodar o terminal, os testes e o git. Como: ligue a Tela do bot e dê acesso à pasta do projeto; sem ela o programador explica o que falta e não finge ter rodado nada.
- **Repositório de código (git)** (obrigatório): buscar a última versão e enviar as mudanças. Como: deixe o git do computador autenticado no repositório do projeto (por exemplo, com a CLI do GitHub); o bot pede o login pelo cartão de entrada, sem a senha passar pelo chat.
- **Hospedagem** (opcional): publicar o site ou a plataforma. Como: entre na CLI da hospedagem que você usa (por exemplo, a do Cloudflare) no computador do bot; sem isso o bot deixa a mudança pronta e pede a publicação a você.
- **GitHub** (opcional): abrir pedidos de merge e ler issues. Como: em Apps conectados, ligue o app do GitHub e entre com a sua conta (depois ligue a chave Apps conectados do bot em Configurações → Acesso).
- **Atendimento** (opcional): receber relatos de erro de clientes com as evidências e um patch. Como: adicione ao mesmo workspace o modelo ATENDIMENTO, que está em Modelos, na barra lateral.

[README do modelo](teams/programador/README.md)

### PROJETISTA DE ROBÔS

Projetista que desenha bots novos com você: função, instruções, habilidades, ferramentas, automações e riscos, em uma ficha pronta para criar no Nordus.

**Antes de usar:**

- **Busca na web e navegador** (opcional): ler a documentação das ferramentas que o bot novo vai usar. Como: ative a busca na web e o navegador nas configurações do bot; sem eles o projetista desenha só com o que você contar e marca o resto como a confirmar.
- **Tela do bot** (opcional): guardar as fichas dos bots. Como: ligue a Tela do bot; sem ela a ficha sai na conversa.
- **Boss do time** (opcional): criar o bot a partir da ficha, direto pelo chat. Como: marque um bot do time como Boss no menu do bot; sem Boss, você cria pelo botão Novo bot colando a ficha.

[README do modelo](teams/projetista-de-robos/README.md)

### SOCIAL MEDIA

Social media que planeja o conteúdo, pede design e vídeo ao time, leva tudo para a sua aprovação na conversa e só agenda o que você liberar.

**Antes de usar:**

- **Agendador de redes sociais** (obrigatório): agendar e conferir os posts aprovados e olhar a grade antes de marcar um horário. Como: em Apps conectados, ligue o conector da ferramenta de agendamento que você usa e entre com a conta (depois ligue a chave Apps conectados do bot em Configurações → Acesso); sem ele o bot trabalha até a aprovação e deixa tudo pronto para você postar.
- **Designer gráfico e Editor de vídeo** (opcional): receber as peças de design, a capa do reel e os vídeos que o social media pede. Como: adicione ao mesmo workspace os modelos DESIGNER GRÁFICO e EDITOR DE VÍDEO, que estão em Modelos, na barra lateral; sem eles o bot monta o briefing completo e entrega a você.
- **Estrategista de conteúdo e Pesquisador** (opcional): trazer pautas, ideias, copy e pesquisa com fonte. Como: adicione ao mesmo workspace os modelos ESTRATEGISTA DE CONTEÚDO e PESQUISADOR, que estão em Modelos, na barra lateral; sem eles o social media escreve a pauta e a copy sozinho.
- **Tela do bot** (opcional): guardar a ficha de cada marca e os arquivos dos posts. Como: ligue a Tela do bot; sem ela o trabalho segue na conversa e o histórico não fica guardado.

[README do modelo](teams/social-media/README.md)

### TRÁFEGO PAGO

Time de nove bots que abre o projeto, testa criativos, opera a conta da Meta dentro de um teto e reporta o retorno, com revisão de política antes do ar.

**Antes de usar:**

- **Meta Ads** (obrigatório): ler resultados e operar a conta de anúncios. Como: em Apps conectados, ligue o conector de Meta Ads e entre com a conta que administra os anúncios (depois ligue a chave Apps conectados do bot em Configurações → Acesso).
- **Tela do bot** (obrigatória): guardar a ficha de cada projeto em arquivos (o time cria a pasta projetos sozinho). Como: ligue a Tela do bot em cada bot do time.
- **Vendas reais** (opcional): medir o retorno no caixa (gateway de pagamento ou plataforma de vendas, ou um relatório de vendas que você envia). Como: conecte a plataforma de vendas em Apps conectados ou envie o relatório de vendas ao gestor; sem isso o time lê só o que a Meta atribui.
- **Editor de vídeo e Designer gráfico** (opcional): produzir as peças de vídeo e de imagem dos anúncios. Como: adicione ao seu workspace os modelos EDITOR DE VÍDEO e DESIGNER GRÁFICO, que estão em Modelos, na barra lateral; o diretor de criativo pede as peças a eles.

[README do modelo](teams/trafego-pago/README.md)

## Autoria e licença

Autor: Nordus. Licença: Apache-2.0.
