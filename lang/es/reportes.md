---
description: Consultar los reportes asociados a las transacciones
---

# Reportes

### Consultar ventas

{% swagger method="post" path="list" baseUrl="/api/v1/transactions/" summary="Servicio que devuelve todas las transacciones de venta en un rango de fechas especifico" expanded="true" %}
{% swagger-description %}
El servicio devuelve un máximo de 1.000 transacciones
{% endswagger-description %}

{% swagger-parameter in="body" name="data" type="Object" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.dateStart" type="string" required="false" %}
YYYY-MM-DD filtro de rango de fecha inicial
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.dateEnd" type="string" required="false" %}
YYYY-MM-DD filtro de rango de fecha final
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.typeReport" type="string" required="true" %}
sales (indica el reporte de ventas)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Respuesta satisfactoria" %}
<pre class="language-javascript"><code class="lang-javascript"><strong>{
</strong>  "status": 200,
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
      "createdAt": "2022-11-21 12:38:00"
    }]
  }
}
</code></pre>
{% endswagger-response %}
{% endswagger %}

### Consultar compras

{% swagger method="post" path="list" baseUrl="/api/v1/transactions/" summary="Servicio que devuelve todas las compras o cargas de saldo en un rango de fechas especifico" expanded="true" %}
{% swagger-description %}
El servicio devuelve un máximo de 1.000 transacciones
{% endswagger-description %}

{% swagger-parameter in="body" name="data" type="Object" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.typeReport" type="string" required="false" %}
buys (valor fijo que indica reporte de compras)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.dateStart" type="string" required="false" %}
Fecha de inicio (YYYYMM-DD)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.dateEnd" type="string" required="false" %}
YYYY-MM-DD filtro de rango de fecha final
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
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
      "amount": 200000,
      "createdAt": "2022-11-21 12:38:00",
    }]
  }
}
```
{% endswagger-response %}
{% endswagger %}
