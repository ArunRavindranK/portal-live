---
description: >-
  API to check whether the sim and device binding is completed at the backend
  server
---

# Check status API

{% swagger method="get" path="" baseUrl="<domain>/onboarding/user/auth/checkStatus/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-KEYREF-VAL" required="true" %}
Key reference value received from backend while calling

[save encrypyted payload api](save-encrypted-payload-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[login API](../authentication-and-authorization/login-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request GET 'http://localhost:8083/onboarding/user/auth/checkStatus/v1' \
\--header 'X-KEYREF-VAL: 202205aLEdeXaEYC'
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'X-API-TOKEN: token' 
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "response": "SUCCESS"
    }
}
```
{% endtab %}
{% endtabs %}
