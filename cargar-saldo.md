# 💸 Cargar saldo

{% swagger method="post" path="generateLink" baseUrl="transactions/payment/" summary="Servicio que genera un link de pago" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="data.reference" required="false" %}
Referencia de pago
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.amount" required="false" %}
Valor a recaudar
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.confirmUrl" required="false" %}
URL del webhook donde se notificará
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.responseUrl" required="false" %}
URL donde el usuario será redirigo luego de pagar
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "data": {
        "link": "https://bemovil.net/payment/ID"
    }
}
```
{% endswagger-response %}
{% endswagger %}

#### Al WebHook compartido por el cliente se enviará el siguiente Request:

```json
{
    "data": {
        "id": "eff0340c-6146-4863-afd7-9b93b1e68b71", // ID de Bemovil,
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
