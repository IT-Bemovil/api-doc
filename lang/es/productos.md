---
description: >-
  Servicios que permiten consultar productos, comisiones, imágenes, datos para
  reconstruir la vista a nivel gráfico, etc.
---

# Productos

## Servicio que permite consultar productos y su comisión asignada

<mark style="color:green;">`POST`</mark> `/api/v1/products/list`

#### Request Body

| Name                                   | Type   | Description |
| -------------------------------------- | ------ | ----------- |
| data<mark style="color:red;">\*</mark> | Object |             |

{% tabs %}
{% tab title="200: OK Respuesta exitosa" %}
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
{% endtab %}
{% endtabs %}

## Servicio que permite obtener toda la información a detalle de un producto

<mark style="color:green;">`POST`</mark> `/api/v1/products/get`

Note: El campo "options" devuelve la información necesaria para reconstruir la vista a nivel gráfico

#### Request Body

| Name                                             | Type   | Description                |
| ------------------------------------------------ | ------ | -------------------------- |
| data.productId<mark style="color:red;">\*</mark> | string | Identificador del producto |

{% tabs %}
{% tab title="200: OK Respuesta exitosa" %}
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
{% endtab %}
{% endtabs %}
