---
description: >-
  Essa é a requisição que seu Endpoint recebe quando um jogador der um "giro"
  (Fizer uma Bet) em qualquer jogo dentro do seu Casino.
---

# 🪙 game\_callback

`/gold_api/game_callback`

### <mark style="color:green;">`WEBHOOK`</mark> Pós-Bet (game\_callback)

{% code title="Resposta da API" %}
```json
{
  "agent_secret": "Token do Agent",
  "user_code": "Còdigo do Jogador",
  "user_balance": Saldo do Jogador,
  "user_total_credit": Total Ganho pelo Jogador,
  "user_total_debit": Total Apostado pelo Jogador,
  "game_type": "slot",
  "slot": {
    "provider_code": "Código do Provedor",
    "game_code": "Código do Game",
    "round_id": "Código Único da Sessão",
    "type": "BASE",
    "bet": Valor do Giro,
    "win": Valor Ganho,
    "txn_id": "Código Único do Giro",
    "txn_type": "Tipo de Jogada",
    "is_buy": Bet Comprada Sim ou Não,
    "is_call": Bet Bônus Sim ou Não,
    "user_before_balance": Saldo do Jogador Antes do Giro,
    "user_after_balance": Saldo do Jogador Após o Giro,
    "agent_before_balance": Saldo do Agent Antes do Giro,
    "agent_after_balance": Saldo do Agent Após o Giro,
    "created_at": "Data de Criação da Bet"
  }
}
```
{% endcode %}

Você usará essas informações para criar e modificar dados no seu <mark style="color:green;">Banco de Dados</mark>. Utilize as informações da `Bet` para criar uma nova <mark style="color:orange;">`Transação`</mark> no <mark style="color:green;">Banco de Dados</mark> e alterar o <mark style="color:orange;">`Saldo do seu Jogador`</mark>;

### :white\_check\_mark: Exemplo de Webhook Recebido

{% code title="Exemplo" %}
```json
{
  "agent_secret": "f87b1290-1a9f-fw43-9e03-c2c595a6d787",
  "user_code": "213",
  "user_balance": 40,
  "user_total_credit": 278.18,
  "user_total_debit": 588.2,
  "game_type": "slot",
  "slot": {
    "provider_code": "PGSOFT",
    "game_code": "fortune-ox",
    "round_id": "9d2bfwq39eb8182b",
    "type": "BASE",
    "bet": 5,
    "win": 0,
    "txn_id": "a1gfk413-d5d3-1a89-a5bd-495g9a244db0",
    "txn_type": "debit_credit",
    "is_buy": false,
    "is_call": false,
    "user_before_balance": 40,
    "user_after_balance": 35,
    "agent_before_balance": 100,
    "agent_after_balance": 100,
    "created_at": "2024-07-29T16:50:32.506Z"
  }
}
```
{% endcode %}

