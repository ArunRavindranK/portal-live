---
description: >-
  Api to Check user holds the Wallet card or not , if user holds wallet card it
  returns wallet Id
---

# Check Wallet card Details API

{% swagger method="post" path="" baseUrl="<domain>/wallet/internal/check/wallet/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="String" required="true" %}
Mobile
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" type="String" required="true" %}
Product Type(wallet type ex: RW)
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

| Response code | Response description                |
| ------------- | ----------------------------------- |
| 21            | product type is empty               |
| 100           | Card Not found                      |
| 150           | Mobile# or Customer Id is Mandatory |

| <p><br>Card Validated Successfully</p> |
| -------------------------------------- |

{% tabs %}
{% tab title="Sample curl command" %}
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/internal/check/wallet/v1'

\\--header 'Content-Type: text/plain'

```
\--header 'X-API-KEY: MOB-APP-2001'
```

\\--header 'X-API-TOKEN:token' --data-raw '{ "mobile": "string", "productType": "string" }'​
{% endtab %}

{% tab title="Request" %}
```
{
  "mobile": "string",
  "productType": "string"
}
```
{% endtab %}

{% tab title="Response" %}
200 -> Card Validated Successfully

201 -> Created

400 -> request is empty

401 -> Unauthorized

403 -> Forbidden

404 -> Not Found

500 -> INTERNAL ERROR
{% endtab %}
{% endtabs %}
