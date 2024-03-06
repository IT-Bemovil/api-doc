# 💔 Errores

### Estructura de los errores

Los errores siempre contarán con la siguiente estructura:

```json
{
  "errorMessage": "Descripción del error"
  "path": "/api/v1/som/path",
  "date": 123123123, // UNIX FORMAT
  "errorCode": "undefined.error"
}
```

### Manejo HTTP Status Code

Estos serán dados por el HTTP status Code

| Http Status Code |                                 |
| ---------------- | ------------------------------- |
| 200              | OK                              |
| 400              | Error del usuario               |
| 401              | Error de autenticación          |
| 404              | Error  de recurso no encontrado |
| 500              | Error del servidor              |



### Manejo de timeout

El timeout definido máximo para una transacción será de 60 segundos



