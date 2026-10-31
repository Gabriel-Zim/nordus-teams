---
name: conexoes-e-requisitos-do-bot
description: "Listar as ferramentas de que um bot precisa e ensinar a conectar: o que é obrigatório e o que é opcional, quais viram requisito de app (só o rótulo), quais viram conexão MCP com endereço público e só o nome dos valores pedidos, o texto de 'Antes de usar' e a regra de a alma explicar como conectar em vez de falhar. Use quando pedirem 'que ferramentas esse bot precisa', 'como ele se conecta ao X' ou 'monta o Antes de usar'."
---

# Conexões e requisitos do bot

Um bot só entrega o que as ferramentas dele permitem. Esta skill levanta o que ele precisa, separa o que é obrigatório do que é opcional e escreve o caminho para a pessoa conectar, sem expor nenhum segredo.

## Quando usar

- "Que ferramentas esse bot precisa?", "como ele se conecta ao X?".
- "Monta o Antes de usar", "escreve o que a pessoa precisa ligar".
- Ao fechar a ficha de um bot ou de um time (veja `desenho-de-novo-bot`).

## Procedimento

1. **Liste cada ferramenta que o trabalho exige** e marque: obrigatória (sem ela o bot não entrega) ou opcional (melhora, mas há caminho sem ela).
2. **Classifique cada uma:**
   - **App conhecido** (por exemplo, e-mail, agenda, arquivos em nuvem, uma ferramenta de design): vira um *requisito de app*, só com o rótulo e o motivo. A pessoa liga em Apps conectados.
   - **Servidor MCP com endereço público**: vira uma *conexão* com o endereço e **só o nome dos valores pedidos** (por exemplo, `Authorization`), nunca o valor. A conexão chega desligada: a pessoa liga e preenche em Apps conectados, aba Conexões avançadas.
   - **Capacidade do próprio app** (busca na web, navegador, Tela do bot): não é conexão. Diga onde ligar nas configurações do bot.
   - **Ferramenta privada de uma casa** (script de servidor, pasta interna): não entra no desenho. Descreva a função de forma genérica ("ferramenta de aprovação e agendamento") ou deixe fora.
3. **Confirme o endereço antes de escrever.** Use só o que a documentação oficial do fornecedor publica. Sem endereço confirmado, escreva só o rótulo e a instrução ("ligue o conector do fornecedor X e entre com a sua conta"). Nunca invente URL nem nome de valor.
4. **Escreva o "Antes de usar"** (na descrição do bot e no README): para cada ferramenta, o que conectar, para quê e onde fica no app, numa linha cada. Marque as obrigatórias.
5. **Escreva a regra na alma:** se uma ferramenta obrigatória não estiver conectada, o bot explica à pessoa, em poucas linhas, como conectar, em vez de falhar ou improvisar outro caminho. Para as opcionais, diga o que muda sem elas.
6. **Confira o que nunca viaja:** valores de chaves e senhas, endereços privados, modelo escolhido, computador, histórico.

## Texto-base para a alma

> Ferramentas: confira antes de começar. Para fazer X preciso do app Y conectado. Se não estiver: "Para isso preciso do Y conectado. Abra Apps conectados (ou a aba Conexões avançadas, se for uma conexão MCP), ligue o Y, entre com a sua conta e ligue a minha chave Apps conectados em Configurações → Acesso." Enquanto isso, trabalhe até onde der sem o Y e diga o que ficou esperando.

## Cuidados

- **Valor de credencial em texto** (chave, token, senha) nunca vai para a ficha, para a alma nem para uma habilidade. Só o nome do valor.
- **Obrigatório demais afasta.** Se o bot funciona sem a ferramenta, marque como opcional e diga o que muda.
- **Aviso vago não ensina.** "Conecte as ferramentas" não diz qual nem onde. Escreva o nome, o motivo e o lugar no app.
- **Bot que improvisa sem a ferramenta** entrega algo que parece pronto e não é. A regra da alma existe para evitar isso.

## Antes de dar por terminado

Cada ferramenta tem rótulo, motivo e se é obrigatória; as conexões trazem endereço público e só o nome dos valores; a alma explica como conectar; e nenhum valor de credencial aparece em lugar nenhum.
