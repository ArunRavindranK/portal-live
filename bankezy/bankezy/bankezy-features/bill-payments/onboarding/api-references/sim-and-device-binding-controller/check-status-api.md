---
description: This API is used to check the Sim and Device binding status.
---

# Check Status API

{% swagger method="get" path="" baseUrl="http://192.168.105.70:8083/onboarding/user/auth/checkStatus/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-KEYREF-VAL" required="true" %}
user Key reference value
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
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

{% swagger-response status="404: Not Found" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Response" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "response": "NOT FOUND"
    }
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request GET 'http://192.168.105.70:8083/onboarding/user/auth/checkStatus/v1' \
\--header 'X-KEYREF-VAL: 2001|3089|[C@5fc133b3'
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
--data-raw ''
```
{% endtab %}
{% endtabs %}
