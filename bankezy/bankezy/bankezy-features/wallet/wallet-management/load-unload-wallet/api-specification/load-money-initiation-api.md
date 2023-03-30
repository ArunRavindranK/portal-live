---
description: Adding Funds into users wallet
---

# Load Money Initiation API



{% swagger method="post" path="" baseUrl="<domain>/orchestrate/lm/init/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="amount" type="String" required="true" %}
Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" type="String" required="true" %}
Product Type(wallet type ex: RW)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
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

## Custom error codes

| Response Code | Response Description                                                     |
| ------------- | ------------------------------------------------------------------------ |
| 20            | ​request is empty                                                        |
| 21            | Customer Id is Mandatory                                                 |
| 27            | Amt should be greater than Zero                                          |
| ​100          | ​EXECUTION FAILURE                                                       |
| 300           | Invalid CategoLoad Money Initiation failed.. Please try after some time. |

{% tabs %}
{% tab title="Sample curl command" %}
curl --location --request POST '[https://payment1.pcdev.enstage-sas.com/orchestrate/lm/init/api/v1'](https://payment1.pcdev.enstage-sas.com/orchestrate/lm/init/api/v1')

\\--header 'Content-Type:text/plain'

\\--header 'X-API-KEY: MOB-APP-2001'

\\--header 'X-API-TOKEN:token'

\--data-raw'{

&#x20; "amount": 100,&#x20;

"customerId": "29",&#x20;

"kycLevel": 30,

&#x20;"productType": "RW"&#x20;

}'
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "amount": 100,
  "customerId": "29",
  "kycLevel": 30,
  "productType": "RW"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "Load Money Initiated Successfully",
  "data": {
    "merchantId": "171756421435003980",
    "merchantName": "Bankezy Wallet Card",
    "merchantTxnId": "202207251403294290xN66vO7"
  }
}
```
{% endtab %}
{% endtabs %}
