---
description: >-
  Api to return Wallet Statement for given criteria (date range, email Id) all
  transactions with closing balance
---

# Fetch Wallet Statement API

{% swagger method="post" path="" baseUrl="<domain>/wallet/fetch/v1/statement" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="emailId" required="false" %}
email Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fromDate" required="false" %}
from Date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="programId" type="Int" required="false" %}
​program Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="toDate" required="false" %}
to Date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userId" required="false" %}
user Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletStatementId" type="Int" required="false" %}
wallet Statement Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletStatus" required="false" %}
wallet Status
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
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/fetch/cvv/api/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-TOKEN:token'
\--header 'X-API-KEY:MOB-APP-2001'
\--data-raw '{"emailId": "abhinav.aradhya@wibmo.com","fromDate": "2022-07-01","programId": 1111,"toDate": "2022-07-25","userId": "29","walletStatementId": 1,"walletStatus": "Active"}'​
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "emailId": "abhinav.aradhya@wibmo.com",
  "fromDate": "2022-07-01",
  "programId": 1111,
  "toDate": "2022-07-25",
  "userId": "29",
  "walletStatementId": 1,
  "walletStatus": "Active"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "Pdf generated initiated, you will receive it on mail"
}
```
{% endtab %}
{% endtabs %}
