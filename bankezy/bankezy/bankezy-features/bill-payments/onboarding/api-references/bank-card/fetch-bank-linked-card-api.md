---
description: This API is used to fetch the sim card from bank.
---

# Fetch bank linked card API

{% swagger method="get" path="" baseUrl="http://192.168.105.70:8083/onboarding/bank/fetchBankLinkedCards/v1" summary="" %}
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
{% tab title="Request" %}
```json
{
    "accountNumber" : "1501"
}
```
{% endtab %}

{% tab title="Response" %}
```json
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "bankResp": "Successfully fetch account details",
        "bankName": "HDFC",
        "cardNumber": "2233445551234"
    }
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request GET 'http://192.168.105.70:8083/onboarding/bank/fetchBankLinkedCards/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: application/json'
```
{% endtab %}
{% endtabs %}
