---
name: politica-de-atendimento
description: "Criar e manter a política de atendimento do produto (atendimento/politica.md): o que o atendimento resolve sozinho, a regra de crédito e reembolso, o que é decisão da pessoa, a voz, as respostas padrão e quem avisar. Use na primeira conversa, quando a política estiver vazia, e quando a pessoa disser 'muda a regra de reembolso', 'adiciona uma resposta padrão' ou 'atualiza a política'."
---

# Política de atendimento

A política é o que autoriza o atendimento a responder sozinho. Sem ela, o atendimento prepara as respostas e espera o ok. Esta skill monta a política com a pessoa e a mantém atualizada.

## Quando usar

- Primeira conversa, ou o arquivo `atendimento/politica.md` não existe ou está vazio.
- "Muda a regra de reembolso", "adiciona uma resposta padrão", "o que o atendimento pode prometer?".
- Um caso novo apareceu e a política não o cobre.

## Procedimento

1. **Entrevista curta, numa mensagem só.** Pergunte: o que o produto faz e quem usa; por onde os clientes escrevem (chat do site, e-mail de suporte) e com que nome a equipe assina; a regra de crédito e de reembolso (o que o atendimento pode devolver sozinho e o que é decisão da pessoa); os prazos típicos dos serviços; as dúvidas mais frequentes e a resposta certa para cada uma; quem deve ser avisado e como.
2. **Escreva a política** neste formato e mostre à pessoa:

```
Produto: (o que é, para quem)
Assinatura da equipe:
Canais: (chat do site, e-mail de suporte)
Voz: (tom, tamanho, o que evitar)
O que o atendimento resolve sozinho:
Crédito e reembolso: (o que devolve sozinho; o que é decisão da pessoa)
Prazos típicos:
Respostas padrão: (dúvida, resposta)
O que nunca dizer ou fazer:
Quem avisar e como:
```

3. **Peça o ok em texto.** Só depois do ok o atendimento passa a responder sozinho dentro dela.
4. **Guarde** em `atendimento/politica.md` (na Tela do bot, se estiver ligada; sem ela, mantenha na conversa e peça que a pessoa a guarde).
5. **Atualize quando um caso novo aparecer:** proponha a mudança em uma frase, espere o ok e só então altere. Não amplie o que o atendimento resolve sozinho sem o ok.

## Cuidados

- **Dinheiro é sempre decisão da pessoa,** a menos que a política diga o contrário de forma explícita e com limite.
- **Nada de promessa na política** que o produto não cumpre.
- **Sem nome de funcionário** nem dado de cliente na política.
- **Resposta padrão é ponto de partida,** não cola e envia: adapte ao que o cliente escreveu.

## Antes de dar por terminado

A política tem todos os campos, a pessoa aprovou em texto e o arquivo está guardado.
