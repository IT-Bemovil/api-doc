# 💸 Cargar saldo



{% swagger method="post" path="generateLink" baseUrl="transactions/payment/" summary="Servicio que genera un link de pago" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="data.reference" %}
Referencia de pago
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.amount" %}
Valor a recaudar
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.confirmUrl" %}
URL del webhook donde se notificará
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.responseUrl" %}
URL donde el usuario será redirigo luego de pagar
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "data": {
        "link": "https://pronty.co/payment/ID"
    }
}
```
{% endswagger-response %}
{% endswagger %}



#### Al WebHook compartido por el cliente se enviará el siguiente Request:

```json
{
    "data": {
        "id": "eff0340c-6146-4863-afd7-9b93b1e68b71", // ID de pronty,
        "Amount": {
            "cost": 0,
            "amount": 200000
        },
        "reference": "ABC", // referencia del cliente
        "TransactionStatus": {
            "id": 2,
            "name": "Aprobado"
        },
        "PaymentMethod": {
            "id": 4,
            "name": "PSE"
        },
        "createdAt": "2022-12-20 12:12pm"
    }
}
```

