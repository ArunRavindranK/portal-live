---
description: >-
  This API helps to save the payload which is encrypted by using public key
  shared by server
---

# Save Encrypted Payload API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/auth/saveEncryptedPayLoad/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[login API](../authentication-and-authorization/login-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payLoad" required="true" %}
encrypted payload by using

[public key](public-key-for-sim-and-device-verification-api.md)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "keyForPayload": "202205aLEdeXaEYC",
        "destinationNo": "1234567890",
        "envKeyword": "DEV",
        "programId": 1111
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
curl --location --request POST 'http://localhost:8083/onboarding/user/auth/saveEncryptedPayLoad/v1' \
--header 'X-API-TOKEN: token' \
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Content-Type:text/plain'
--data-raw '{
    "payLoad":"Q9/SfT5crLfrUrgERqlk5FFUHI3SKv8t0AoHTAWxxk8kp5A0VdNMZkOl/WbpI7/K982DU5EsnlyONJ/F8+kpNnZ9kBJ/TizvXsnyL2XShyagRK3tvErAVVjdM0hkuEN9vclx3vEJSvnjUNsgTqFVrn29YJDbrfipNd1syr8vZbY="
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json5
{
    "payLoad":"Q9/SfT5crLfrUrgERqlk5FFUHI3SKv8t0AoHTAWxxk8kp5A0VdNMZkOl/WbpI7/K982DU5EsnlyONJ/F8+kpNnZ9kBJ/TizvXsnyL2XShyagRK3tvErAVVjdM0hkuEN9vclx3vEJSvnjUNsgTqFVrn29YJDbrfipNd1syr8vZbY="
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "keyForPayload": "202205aLEdeXaEYC",
        "destinationNo": "1234567890",
        "envKeyword": "DEV",
        "programId": 1111
    }
}
```
{% endtab %}
{% endtabs %}
