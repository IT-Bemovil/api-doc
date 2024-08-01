---
description: >-
  Services that allow querying products, commissions, images, data for
  reconstructing the graphical view, etc.
---

# Products

## Service that allows querying products and their assigned commission.

<mark style="color:green;">`POST`</mark> `/api/v1/products/list`

#### Request Body

| Name                                   | Type   | Description |
| -------------------------------------- | ------ | ----------- |
| data<mark style="color:red;">\*</mark> | Object | Data field  |

{% tabs %}
{% tab title="200: OK Successful" %}
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
{% endtab %}
{% endtabs %}

## Service that allows obtaining all detailed information about a product.

<mark style="color:green;">`POST`</mark> `/api/v1/products/get`

Note: The "options" field returns the necessary information to reconstruct the graphical view.

#### Request Body

| Name                                             | Type   | Description |
| ------------------------------------------------ | ------ | ----------- |
| data.productId<mark style="color:red;">\*</mark> | string | Product ID  |

{% tabs %}
{% tab title="200: OK Successful" %}
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
