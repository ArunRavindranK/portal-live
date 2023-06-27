---
description: This API helps to initiate a transaction in bankEzy
---

# Payment Param API

{% swagger method="post" path="" baseUrl="<domain>/payments/params/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="long" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="int" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionType" type="String" required="true" %}
Transaction type
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
{% endswagger %}

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request POST 'http://localhost:2442/
payments/params/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=1EFD299E213DEE8847A52413CD0FB47E' \
--data-raw '{
    "transactionType":"TC"
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "transactionType":"TC"
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": "200",
    "resDesc": "SUCCESS",
    "data": {
        "pgImplementation": "Redirect",
        "redirectFormAction": "https://user4.pcdev.enstage-sas.com/kong/redirect/payments/v1/txn/connect/pg",
        "merchantKey": "null",
        "salt": "null",
        "productInfo": "null",
        "merchantId": "81516123",
        "merchantName": "Card Management Merchant",
        "surl": "null",
        "furl": "null"
    }
}
```
{% endtab %}
{% endtabs %}
