---
description: Fetch Beneficiary Accounts By Beneficiary Id
---

# Fetch Beneficiary Accounts By Beneficiary Id API

{% swagger method="get" path="" baseUrl="<domain>/wallet/ac/v1/fetch/specificBeneficiary" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" %}
The token got from the login API
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

## Custom response codes

| Code | Description                         |
| ---- | ----------------------------------- |
| ​150 | ​Beneficiary Accounts not available |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request GET 'https://payment1.pcdev.enstage-sas.com/wallet/ac/v1/fetch/specificBeneficiary'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --header 'BENEFICIARY-ID:42'​
```
{% endcode %}
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "SUCCESS",
  "data": {
    "id": 42,
    "customerId": "2022",
    "accountNumber": null,
    "accountName": null,
    "ifscCode": null,
    "vpa": "8892239811@bankezy",
    "bankName": null,
    "accountType": null,
    "branchName": null,
    "createdTime": "2022-04-05T13:13:44.000+00:00",
    "updatedTime": null
  }
}
```
{% endtab %}
{% endtabs %}
