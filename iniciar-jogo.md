---
description: Nessa página você verá um exemplo de Requisição para Iniciar um Jogo.
---

# 🎮 Iniciar Jogo

## Parâmetros da Requisição

<mark style="color:green;">`POST`</mark> `/api/v1/game_launch`\
\
`Header` | <mark style="color:orange;">`"Content-Type: application/json"`</mark>

:warning: **Para enviar Saldo do Jogador com decimais**, envie usando <mark style="color:green;">"." (ponto)</mark> e não <mark style="color:red;">"," (vírgula)</mark>;\
Caso envie com vírgula invés de ponto, você terá erro na chamada! <mark style="color:green;">`Ex: R$10.50`</mark>

:page\_facing\_up: **Corpo da Chamada `(Body)`**

<table><thead><tr><th>Campo</th><th>Valor</th><th data-type="checkbox">Obrigatório</th></tr></thead><tbody><tr><td>agentToken</td><td><code>Token do Agent</code></td><td>true</td></tr><tr><td>secretKey</td><td><code>Secret_Key do Agent</code></td><td>true</td></tr><tr><td>user_code</td><td><code>Código do Usuário</code></td><td>true</td></tr><tr><td>provider_code</td><td><code>Código do Provedor</code></td><td>false</td></tr><tr><td>game_code</td><td><code>Código do Jogo</code></td><td>true</td></tr><tr><td>user_balance</td><td><code>Saldo do Usuário</code></td><td>true</td></tr></tbody></table>

### <mark style="color:orange;">`JSON`</mark>  Exemplo de Requisição:

{% code title="Request:" %}
```json
{
    "agentToken": "9bab1794-c0d5-4281-9bcf-12e83b3e0d12",
    "secretKey": "a67ee57a-6f46-4e9f-b985-0ea7f21e48fa",
    "user_code": 597,
    "provider_code": "0",
    "game_code": "fortune-dragon",
    "user_balance": 76.35
}
```
{% endcode %}

### <mark style="color:orange;">`JSON`</mark>  Exemplo de Resposta :

{% code title="Response:" %}
```json
{
    "status": "sucess",
    "game_url": "https://provedor-api/1234567/index.html?operator_token=W12f22fb=&btt=1&t=9bab1794-c0d5-4281-9bcf-12e83b3e0d12&or=provedor.api&api=provedor.api"
}
```
{% endcode %}

### <mark style="color:orange;">`cURL`</mark>  Chamada Pronta:

{% code title="Chamada cURL" %}
```json
curl -X POST https://provedor.api.com/api/v1/game_launch \
-H "Content-Type: application/json" \
-d '{
    "agentToken": "9bab1794-c0d5-4281-9bcf-12e83b3e0d12",
    "secretKey": "a67ee57a-6f46-4e9f-b985-0ea7f21e48fa",
    "user_code": 597,
    "provider_code": "0",
    "game_code": "fortune-dragon",
    "user_balance": 76.35
}'
```
{% endcode %}

