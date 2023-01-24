# 🛵 Domicilios

{% swagger method="post" path="quoteDelivery" baseUrl="/api/v1/orders/" summary="" expanded="true" %}
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
{% endswagger %}
