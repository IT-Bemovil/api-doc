# 🔓 Autenticación

### Ambientes API

#### Ambiente productivo

Url de producción para efectuar transacciones reales

{% hint style="info" %}
https://apiv2.bemovil.net
{% endhint %}

#### Ambiente de pruebas

Url de pruebas para efectuar transacciones de prueba

{% hint style="info" %}
https://apiv2.sandbox.bemovil.net
{% endhint %}

### Autorización

La forma de autenticación será por headers en el campo "Authorization", el token será proporcionado por la empresa

```json
{
  "Headers": {
    "Authorization": "Bearer TOKEN"
  }
}
```
