# Examples

<details>

<summary>Sell topup</summary>

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

<summary>Sell Betplay</summary>

El campo \_geolocation se valida si el producto está activo contra la ciudad más cercana

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

</details>

<details>

<summary>Sell bill invoices</summary>

```json
{
  "data": {
    "productId": 527611,
    "reference": "8612312",
    "customerCellphone": "3148527176"
    "amount": 29500
  },
  "_version": "1.10.2",
  "_channel": "WS",
  "_geolocation": null
}
```

</details>

<details>

<summary>Sell giftcodes</summary>

```json
  "data": {
    "productId": 101001,
    "customerCellphone": "3148527176",
    "customerEmail": "luis.correal@bemovil.net",
    "amount": 20000
  },
  "_version": "1.10.2",
  "_channel": "WS",
  "_geolocation": null
}
```

</details>

<details>

<summary>Sell mobile packages</summary>

```json
{
  "data": {
    "productId": 20043,
    "customerCellphone": "3148527176",
    "amount": 16000
  },
  "_deviceId": "6c7ec409-249a-4f21-9a92-720e441fd998",
  "_version": "1.10.2",
  "_channel": "WS",
  "_geolocation": null
}
```

</details>

<details>

<summary>Bank deposits</summary>

```jsonp
{
  "data": {
    "productId": 411001,
    "amount": 300000,
    "accountType": "1",
    "accountNumber": "666777666",
    "customerCellphone": "3148527176",
    "customerDocument": "1198674521"
  },
  "_channel": "WS",
  "_geolocation": {
    "lat": 4.551174364972845,
    "lon": -75.66465588419928,
    "accuracy": 124
  }
}
```

</details>
