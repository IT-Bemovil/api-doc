---
description: Consultar los reportes asociados a las transacciones
---

# 📅 Reportes



### Consultar ventas

{% swagger method="post" path="sales" baseUrl="/api/v1/transactions/reports/" summary="Servicio que devuelve todas las transacciones de venta en un rango de fechas especifico" expanded="true" %}
{% swagger-description %}
El servicio devuelve un máximo de 1.000 transacciones
{% endswagger-description %}

{% swagger-parameter in="body" name="data" type="Object" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.dateStart" type="string" %}
YYYY-MM-DD filtro de rango de fecha inicial
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.dateEnd" type="string" %}
YYYY-MM-DD filtro de rango de fecha final
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Respuesta satisfactoria" %}
```javascript
{
  "status": 200,
  "data": {
    "Transactions": [{
      "id": 1,
      "TransactionsStatus": {
        "id": 1,
        "name": "Exitoso"
      },
      "Product": {
        "id": 10000,
        "name": "Claro"
      },
      "amount": 2000,
      "dateStart": "2022-11-21 12:38:00",
      "dateEnd": "2022-11-21 12:39:00",
      "reference": "A1" // Referencia de venta
    }]
  }
}
```
{% endswagger-response %}
{% endswagger %}
