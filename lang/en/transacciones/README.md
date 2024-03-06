---
description: >-
  Service group for viewing a transaction, checking balances, creating a new
  transaction, and more.
---

# Transactions

{% swagger method="post" path="getBusiness" baseUrl="/api/v1/commerces/" summary="Service that returns the available balances in the account." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="data" type="Object" %}
data field
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Succesful response" %}
```json
{
  "statusCode":200,
  "message": "Sucessful",
  "data": { 
    "Business": {
      "balance":12000,
      "profits":2300
    }
  },
  "_channel": "web"
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="find" baseUrl="/api/v1/transactions/" summary="Service that returns all the information about a transaction." expanded="true" %}
{% swagger-description %}
This service returns information about a transaction if it was carried out within the last two days.
{% endswagger-description %}

{% swagger-parameter in="body" name="data" type="Object" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="_id" required="false" %}
Customer ID (the same as sent in the sale)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Sucessful" %}
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

{% swagger-response status="404: Not Found" description="Transaction not found" %}
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

### Status transaction

| Estado     | Codigo |
| ---------- | ------ |
| PENDING    | 1      |
| APPROVED   | 2      |
| REJECTED   | 3      |
| PROCESSING | 4      |
| PARTIAL    | 5      |

### Sell a product

{% swagger method="post" path="sell" baseUrl="/api/v1/transactions/" summary="Service used to initiate a sale" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="data.productId" type="String" required="false" %}
Product ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.*" type="String" required="false" %}
Additional fields required for the product can be consulted here.



[#servicio-que-permite-obtener-toda-la-informacion-a-detalle-de-un-producto](../../es/productos.md#servicio-que-permite-obtener-toda-la-informacion-a-detalle-de-un-producto "mention")
{% endswagger-parameter %}

{% swagger-parameter in="body" name="_channel" type="string" required="false" %}
Always send "WS"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="_version" required="false" %}
API version
{% endswagger-parameter %}

{% swagger-parameter in="body" required="false" name="_id" %}
customer ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Sucessful" %}
```json
{
  "message": "Exitoso",
  "_channel": "WS",
  "statusCode": 200,
  "data": {
    "transactionId": "5d2fa66e-4c73-4f86-b698-6bd5fd5284b1"
  }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="transaction error" %}
```json
{
  "path":"/sell",
  "date":1671479625960,
  "errorCode":"provider.error",
  "message":"Número no es del operador"
}
```
{% endswagger-response %}
{% endswagger %}

### Inquire / Quote

{% swagger method="post" path="query" baseUrl="/api/v1/transactions/" summary="Service that allows for quoting and obtaining the sale value" expanded="true" %}
{% swagger-description %}
It is recommended to always consume this service, even if the product does not require a prior inquiry.
{% endswagger-description %}

{% swagger-parameter in="body" name="data.productId" required="true" %}
Product ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.*" required="false" %}
Additional fields required for the product can be consulted here.



[#servicio-que-permite-obtener-toda-la-informacion-a-detalle-de-un-producto](../../es/productos.md#servicio-que-permite-obtener-toda-la-informacion-a-detalle-de-un-producto "mention")
{% endswagger-parameter %}

{% swagger-parameter in="body" name="_channel" required="false" %}
Always send "WS"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="_version" required="false" %}
API version
{% endswagger-parameter %}
{% endswagger %}
