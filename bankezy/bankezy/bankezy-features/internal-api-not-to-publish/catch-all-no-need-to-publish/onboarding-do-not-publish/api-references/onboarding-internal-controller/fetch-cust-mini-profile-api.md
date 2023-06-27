---
description: This API is used to get customer mini profile details.
---

# Fetch-Cust-Mini-Profile API

{% swagger method="get" path="" baseUrl="http://192.168.105.70:8083/onboarding/internal/fetch-cust-mini-profile/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
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
    "resDesc": "Success",
    "data": {
        "firstName": "Bal",
        "lastName": "Mahto",
        "mobileNo": "7827737375",
        "emailId": "bablu.krishana123@gmail.com",
        "kycLevel": 100,
        "customerId": "3089"
    }
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request GET 'http://192.168.105.70:8083/onboarding/internal/fetch-cust-mini-profile/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
```
{% endtab %}
{% endtabs %}
