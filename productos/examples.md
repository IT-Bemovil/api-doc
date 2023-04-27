# Examples

<details>

<summary>Vender Recarga</summary>

```json
{
  "data": {
    "productId": 10000,
    "customerCellphone": "32212341010",
    "amount": 1000
  },
  "_version": "1.7.13",
  "_channel": "WS",
  "_geolocation": null
}
```

</details>

<details>

<summary>Vender Betplay</summary>

El campo \_geolocation se valida si el producto está activo contra la ciudad más cercana

{% code lineNumbers="true" %}
```json
{
  "data": {
    "productId": 206000,
    "customerDocument": "123456",
    "customerCellphone": "32212341010",
    "amount": 1000
  },
  "_version": "1.7.13",
  "_channel": "WS",
  "_geolocation": {
    "commerceId": 10,
    "address": "Calle 10",
    "lat": 35.9501734,
    "lon": 14.413812,
    "accuracy": 15.321
  }
}
```
{% endcode %}

</details>
