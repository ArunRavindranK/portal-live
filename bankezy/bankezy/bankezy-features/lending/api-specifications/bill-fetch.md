---
description: >-
  This API list down the Bill info for the user. It gets the Billed amount,
  Billing period and due date for the user.
---

# Bill Fetch

{% swagger method="get" path="" baseUrl="/lending/v1/bill" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
Token got from Validate Token API
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
{% tab title="Sample Curl Request" %}
```json
curl --location --request GET 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/bill' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: <REPLACE_WITH_TOKEN_FROM_VALIDATE_TOKEN_API_RESPONSE>'
```
{% endtab %}

{% tab title="Response Example" %}
```json
{
    "resCode": "LND_200",
    "resDesc": "SUCCESS",
    "data": {
        "availableLimit": 93500,
        "name": "Ankit Prakash",
        "bill": {
            "startDate": 1640131200000,
            "endDate": 1663804800000,
            "dueDate": 0,
            "amount": 234400,
            "minimumAmountDue": 23300,
            "interest": null,
            "processingFee": null
        }
    }
}
```
{% endtab %}
{% endtabs %}
