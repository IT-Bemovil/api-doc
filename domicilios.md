# 🛵 Domicilios



{% swagger method="post" path="quoteDelivery" baseUrl="/api/v1/orders/" summary="Cotizar domicilio" expanded="true" %}
{% swagger-description %}
Este servicio se usa para cotizar un servicio, además devuelve los kilometros y tiempo estimado de entrega
{% endswagger-description %}

{% swagger-parameter in="body" name="data.Origin.latitude" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Origin.longitude" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Origin.address" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Origin.reference" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Destiny.latitude" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Destiny.longitude" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Destiny.address" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Destiny.reference" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Customer.name" required="true" %}
Nombre del cliente
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Customer.cellphone" %}
Celular del cliente
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Package.size" required="true" %}
Tamaño del paquete\
1- Pequeño\
2 - Mediano

3 - Grande
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Package.declaredValue" required="true" %}
Valor declarado del paquete
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Respuesta exitosa" %}
```javascript
{
    "Quote": {
        "amount": 5000,
        "distance": 3,
        "time": 35
    }
}
```
{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="requestDelivery" baseUrl="/api/v1/orders/" summary="Solicitar servicio" expanded="true" %}
{% swagger-description %}
Este servicio sirve para solicitar un servicio, además devuelve una URL de seguimiento y monitoreo del servicio
{% endswagger-description %}

{% swagger-parameter in="body" name="data.Origin.latitude" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Origin.longitude" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Origin.address" required="true" %}
Dirección de recogida
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Origin.reference" %}
Referencia para recoger el servicio
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Destiny.latitude" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Destiny.longitude" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Destiny.address" required="true" %}
Dirección de entrega
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Destiny.reference" %}
Referencia geo locativa para el driver
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Customer.name" required="true" %}
Nombre de quien se entrega el servicio
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data.Customer.cellphone" required="true" %}
Celular de la persona que recibe el servicio
{% endswagger-parameter %}
{% endswagger %}
