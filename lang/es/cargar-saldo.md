# Cargar saldo

## Servicio que genera un link de pago

<mark style="color:green;">`POST`</mark>  `api/v1/transactions/payment/generateLink`

#### Request Body

| Name             | Type   | Description                                       |
| ---------------- | ------ | ------------------------------------------------- |
| data.reference   | String | Referencia de pago                                |
| data.amount      | String | Valor a recaudar                                  |
| data.confirmUrl  | String | URL del webhook donde se notificará               |
| data.responseUrl | String | URL donde el usuario será redirigo luego de pagar |

{% tabs %}
{% tab title="200: OK " %}
```javascript
{
    "data": {
        "link": "https://bemovil.net/payment/ID"
    }
}
```
{% endtab %}
{% endtabs %}

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
