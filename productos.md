---
description: >-
  Servicios que permiten consultar productos, comisiones, imágenes, datos para
  reconstruir la vista a nivel gráfico, etc.
---

# 😁 Productos

{% swagger method="post" path="list" baseUrl="/apiv1/products/" summary="Servicio que permite consultar productos y su comisión asignada" expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="data" required="true" type="Object" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Respuesta exitosa" %}
```javascript
{
  "statusCode":200,
  "message":"Exitoso",
  "data":{
    "Categories": [
      {
        "id":6,
        "name":"Pines",
        "sort":2,
        "Products": [
          {
            "id":101000,
            "name":"Pines Netflix",
            "image":"/images/netflix.png",
            "description":"Venta de pines netflix",
            "price":null,
            "categoryId":6,
            "tip":3
          }
        ]
      }
    ]
  },
  "_channel":"web"
}
```
{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="get" baseUrl="/api/v1/products/" summary="Servicio que permite obtener toda la información a detalle de un producto" expanded="true" %}
{% swagger-description %}
Note: El campo "options" devuelve la información necesaria para reconstruir la vista a nivel gráfico
{% endswagger-description %}

{% swagger-parameter in="body" name="data" type="Object" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Respuesta exitosa" %}
```javascript
{
  "statusCode":200,
  "message": "Exitoso",
  "data":{
    "id": 10000,
    "name": "Claro",
    "price": 20000,
    "image": "/images/claro.png",
    "description": "Recargas moviles",
    "options": {
      "view": {
        "title": "Realizar recarga",
        "form": {
          "button": "Vender recarga",
          "inputs": [
            { "type": "cellphone", "label": "Celular del cliente", "name": "customerCellphone", "icon": "cellphone"  },
            { "type": "amount", "label": "Valor", "name": "amount", "icon": "price"  }
          ]
        }
      }
    }
  },
  "_channel":"web"
}
```
{% endswagger-response %}
{% endswagger %}



