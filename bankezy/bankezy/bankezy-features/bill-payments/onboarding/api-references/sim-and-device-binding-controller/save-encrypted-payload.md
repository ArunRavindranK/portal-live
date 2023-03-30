---
description: This API is used to save encrypted pay load details.
---

# Save Encrypted PayLoad

{% swagger method="post" path="" baseUrl="http://192.168.105.70:8083/onboarding/user/auth/saveEncryptedPayLoad/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payload" required="true" %}
user payload
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
{% tab title="Request" %}
```
{
    "payload": "replace with actual payload"
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "keyForPayload": "202209o0fDUrfzbA",
        "destinationNo": "1234567890",
        "envKeyword": "DEV",
        "programId": 2001
    }
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'http://192.168.105.70:8083/onboarding/user/auth/saveEncryptedPayLoad/v1' \
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'Content-Type: application/json'
--data-raw '{{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "keyForPayload": "202209o0fDUrfzbA",
        "destinationNo": "1234567890",
        "envKeyword": "DEV",
        "programId": 2001
    }
}
    "payLoad" : "123"
}'
```
{% endtab %}
{% endtabs %}
