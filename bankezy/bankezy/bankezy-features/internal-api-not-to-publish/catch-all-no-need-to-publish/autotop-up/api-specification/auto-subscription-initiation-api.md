---
description: Auto Subscription Initiation
---

# Auto Subscription Initiation API



{% swagger method="post" path="" baseUrl="<domain>/wallet/autoTopup/subscription/init/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-TOKEN" type="String" %}
​The token got from the 

[login API](https://teams.microsoft.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/~/changes/1N4jHPuBZcVMjqkduW8F/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/customer-on-boarding/api-reference/authentication-and-authorization/login-api)


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

{% swagger-response status="204: No Content" description="" %}
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Custom response code

| Code | Description                                                              |
| ---- | ------------------------------------------------------------------------ |
| 26   | ​Customer id is empty                                                    |
| 100  | ​Auto Topup subscription Initiation failed.. Please try after some time. |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
​curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/autoTopup/subscription/init/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw'{}'
```
{% endcode %}
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "AutoTopup subscription Initiated Successfully",
  "data": {
    "merchantId": "171756421435003980",
    "merchantName": "Bankezy Wnallet Card",
    "merchantTxnId": "202207190727307011cI54dT8"
  }
}
```
{% endtab %}
{% endtabs %}
