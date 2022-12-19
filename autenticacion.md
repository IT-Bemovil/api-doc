# 🔓 Autenticación

### Ambientes API

#### Ambiente productivo

Url de producción para efectuar transacciones reales

{% hint style="info" %}
https://api.pronty.co
{% endhint %}

#### Ambiente de pruebas

Url de pruebas para efectuar transacciones de prueba

{% hint style="info" %}
https://api.sandbox.pronty.co
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

