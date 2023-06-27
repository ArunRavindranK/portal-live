---
description: Fetch merchant details
---

# Fetch merchant details



{% swagger method="post" path="" baseUrl="<domain>/merchants/details/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER " type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Sample curl command" %}
curl --location --request POST '/payments/merchants/details/v1' --header 'Content-Type: application/json' --header 'X-API-TOKEN:replace\_with\_basic\_auth\_to\_be\_built\_by\_client'
{% endtab %}

{% tab title="Request" %}



{% endtab %}

{% tab title="Response" %}
200 -> OK&#x20;

201 --> Created&#x20;

401 -> Unauthorized&#x20;

403 -> Forbidden&#x20;

404 -> Not Found
{% endtab %}
{% endtabs %}
