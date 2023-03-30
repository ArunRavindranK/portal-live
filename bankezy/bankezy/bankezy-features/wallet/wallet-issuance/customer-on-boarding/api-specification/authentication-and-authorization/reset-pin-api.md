---
description: If user forgots pin, user can able to reset pin by calling this API
---

# Reset Pin API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/resetPin/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[login API](login-api.md)

or

[Get Token API](../../../../../market-place/api-specification/get-token-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pin" required="true" %}
New pin
{% endswagger-parameter %}

{% swagger-parameter in="body" name="signInMode" required="true" %}
Mode of signIn. For this api it should be 1
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "msg": "Pin has been reset successfully"
    }
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
{% endswagger %}

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:10000/onboarding/user/resetPin/v1' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Cookie: JSESSIONID=C0D114845B4EC3A92A840A1B862E96F4'
\--data-raw '{
    "pin":"2222",
    "signInMode":1
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "pin":"2222",
    "signInMode":1
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "msg": "Pin has been reset successfully"
    }
}
```
{% endtab %}
{% endtabs %}
