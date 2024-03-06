---
description: Query the reports associated with transactions.
---

# Reports

### Sell Queries

{% swagger method="post" path="list" baseUrl="/api/v1/transactions/" summary="Service that returns all sales transactions within a specific date range." expanded="true" %}
{% swagger-description %}
The service returns a maximum of 1,000 transactions.
{% endswagger-description %}

{% swagger-parameter in="body" name="data" type="Object" required="true" %}
Data field
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.dateStart" type="string" required="false" %}
YYYY-MM-DD initial date range filter
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.dateEnd" type="string" required="false" %}
YYYY-MM-DD initial date range filter
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.typeReport" type="string" required="true" %}
"sales" (indicates the sales report)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Satisfactory response" %}
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

### Buy queries

{% swagger method="post" path="list" baseUrl="/api/v1/transactions/" summary="Service that returns all purchases or balance loads within a specific date range." expanded="true" %}
{% swagger-description %}
The service returns a maximum of 1,000 transactions.
{% endswagger-description %}

{% swagger-parameter in="body" name="data" type="Object" required="true" %}
Data field
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.typeReport" type="string" required="false" %}
"buys" (fixed value indicating the purchases report)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.dateStart" type="string" required="false" %}
YYYY-MM-DD initial date range filter
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.dateEnd" type="string" required="false" %}
YYYY-MM-DD initial date range filter
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Satisfactory response" %}
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
