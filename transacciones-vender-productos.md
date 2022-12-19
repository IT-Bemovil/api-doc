---
description: >-
  Grupo de servicios para ver una transacción, consultar saldos, crear una nueva
  transacción y más.
---

# 💸 Transacciones - Vender productos



{% swagger method="post" path="accounts" baseUrl="/api/v1/transactions/" summary="Servicio que devuelve los saldos disponibles en la cuenta" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="data" type="Object" %}
Campo data
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Respuesta exitosa" %}
```json
{
  "statusCode":200,
  "message": "Exitoso",
  "data": { 
    "Account": {
      "balance":12000,
      "profits":2300,
      "currency": "COP"
      }
    },
  "_channel": "web"
}
```
{% endswagger-response %}
{% endswagger %}





{% swagger method="post" path="get" baseUrl="/api/v1/transactions/" summary="Servicio que devuelve toda la información de una transacción" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="data" type="Object" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.transactionId" required="true" %}
Id de la transacción a buscar
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Repuesta satisfactoria" %}
```json
{
  "statusCode":200,
  "message": "Exitoso",
  "data": {
    "Transaction": {
      "id": 1,
      "amount": 5000,
      "currency": "COP",
      "costs": 0,
      "prevBalance": 30000,
      "newBalance": 25000,
      "createdAt": "DD/MM/YY HH:mm",
      "Product": {
        "id": 1,
        "name": "Exitoso",
      },
      "TransactionStatus": {
        "id": 1,
        "name": "Exitoso",
        "color": "red"
      },
      "Person": {
        "document": "",
        "cellphone": ""
      },
      "PaymentMethod": {
          "id": 1,
          "image": "",
          "name": "Saldo"
        }
      }
    },
  "_channel": "web"
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Transacción no encontrada" %}
```javascript
{
  "errorMessage": "Transacción no encontrada"
  "path": "/api/v1/transactions/get",
  "date": 123123123,
  "errorCode": "transaction.notFound"
}
```
{% endswagger-response %}
{% endswagger %}



### Estados de una transacción

| Estado       | Codigo |
| ------------ | ------ |
| Pendiente    | 1      |
| Aprobada     | 2      |
| Rechazada    | 3      |
| Procesando   | 4      |
| Pago parcial | 5      |

