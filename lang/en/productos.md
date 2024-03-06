---
description: >-
  Services that allow querying products, commissions, images, data for
  reconstructing the graphical view, etc.
---

# Products

{% swagger method="post" path="list" baseUrl="/apiv1/products/" summary="Service that allows querying products and their assigned commission." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="data" required="true" type="Object" %}
Data field
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful" %}
```javascript
{
  "statusCode":200,
  "message":"Successful",
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

{% swagger method="post" path="get" baseUrl="/api/v1/products/" summary="Service that allows obtaining all detailed information about a product." expanded="true" %}
{% swagger-description %}
Note: The "options" field returns the necessary information to reconstruct the graphical view.
{% endswagger-description %}

{% swagger-parameter in="body" name="data.productId" type="string" required="true" %}
Product ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Successful" %}
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
