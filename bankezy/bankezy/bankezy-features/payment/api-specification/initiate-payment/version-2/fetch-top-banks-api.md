---
description: >-
  For netbanking transaction, this API helps to return top bank details based on
  priority
---

# Fetch Top Banks API



{% swagger method="get" path="" baseUrl="<domain>/payments/nb/v2/list/topbanks" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
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

| Response Field | Field Description                                          | Data type |
| -------------- | ---------------------------------------------------------- | --------- |
| bankName       | Name of the bank                                           | String    |
| bankCode       | Short code of bankName                                     | String    |
| priority       | Level of prioiry at which order bankname shown to the user | Integer   |

#### Custom Response Code

| Response Code | Response Description |
| ------------- | -------------------- |
| PMT200        | Success              |

{% tabs %}
{% tab title="Sample curl command" %}
```
curl --location --request GET 'http://localhost:2442/payments/nb/v2/list/topbanks' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Cookie: JSESSIONID=6856076DB420C282F7DAD1775520791F'
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": [
        {
            "bankName": "HDFC Bank",
            "bankCode": "HDFB",
            "priority": 1
        },
        {
            "bankName": "Axis NB",
            "bankCode": "AXIB",
            "priority": 2
        },
        {
            "bankName": "SBI NB",
            "bankCode": "SBIB",
            "priority": 3
        },
        {
            "bankName": "ICICI",
            "bankCode": "ICIB",
            "priority": 4
        },
        {
            "bankName": "Canara Bank",
            "bankCode": "CABB",
            "priority": 5
        },
        {
            "bankName": "Industrial Development Bank of India (IDBI)",
            "bankCode": "IDBB",
            "priority": 6
        }
    ]
}
```
{% endtab %}
{% endtabs %}
