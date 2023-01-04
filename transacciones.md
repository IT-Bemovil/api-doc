---
description: >-
  Grupo de servicios para ver una transacción, consultar saldos, crear una nueva
  transacción y más.
---

# 💸 Transacciones



{% swagger method="post" path="getBusiness" baseUrl="/api/v1/commerces/" summary="Servicio que devuelve los saldos disponibles en la cuenta" expanded="true" %}
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



### Vender un producto



{% swagger method="post" path="sell" baseUrl="/api/v1/transactions/" summary="Servicio que sirve para originar una venta" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="data.productId" type="String" %}
ID del producto
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.*" type="String" %}
Campos adicionales que requiera el producto 

\




\


pueden ser consultados aquí 

[#servicio-que-permite-obtener-toda-la-informacion-a-detalle-de-un-producto](productos.md#servicio-que-permite-obtener-toda-la-informacion-a-detalle-de-un-producto "mention")


{% endswagger-parameter %}

{% swagger-parameter in="body" name="_channel" type="string" %}
Siempre enviar WS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="_version" %}
Enviar versión del API
{% endswagger-parameter %}

{% swagger-parameter in="body" required="false" name="_id" %}
Id del cliente (para conciliar)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Venta exitosa" %}
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

{% swagger-response status="400: Bad Request" description="Error en la venta" %}
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





### Consultar / Cotizar

{% swagger method="post" path="query" baseUrl="/api/v1/transactions/" summary="Servicio que permite cotizar y obtener el valor de la venta" expanded="true" %}
{% swagger-description %}
Se recomienda siempre consumir este servicio, así el producto no requiera una consulta previa
{% endswagger-description %}

{% swagger-parameter in="body" name="data.productId" required="true" %}
ID del producto
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.*" %}
Campos adicionales que requiera el producto 

\




\


pueden ser consultados aquí 

[#servicio-que-permite-obtener-toda-la-informacion-a-detalle-de-un-producto](productos.md#servicio-que-permite-obtener-toda-la-informacion-a-detalle-de-un-producto "mention")


{% endswagger-parameter %}

{% swagger-parameter in="body" name="_channel" %}
Siempre enviar WS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="_version" %}
Enviar versión del API
{% endswagger-parameter %}
{% endswagger %}
