---
description: Validates the user Linked card Details, like card number, expiry
---

# Validate Linked card Details API



{% swagger method="get" path="" baseUrl="<domain>/wallet/internal/validate/lc/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="cardNumber" type="String" required="true" %}
Card Number
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-TOKEN  " type="String" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardRefId" type="Int" required="true" %}
Card RefId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="expiryMM" type="String" required="true" %}
expiry MM 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="expiryYYYY" type="String" required="true" %}
expiry YYYY 
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

| Response code | Response description       |
| ------------- | -------------------------- |
| ​26           | customer id is empty       |
| 58            | card number is empty       |
| 59            | card expiry mm is empty    |
| 60            | ​card expiry yyyy is empty |
| 66            | card id is empty           |
| 100           | Card Not found             |
| 151           | ​Card number mismatched    |
| 152           | ​Expiry Month mismatched   |
| 153           | ​Expiry Year mismatched    |

| <p><br></p> |
| ----------- |

{% tabs %}
{% tab title="Sample curl command" %}
​curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/internal/validate/lc/v1'

\\--header 'Content-Type: text/plain'

\\--header 'X-API-KEY: MOB-APP-2001'

\\--header 'X-API-TOKEN:token' --data-raw '{ "cardNumber": "string", "cardRefId": 0, "expiryMM": "string", "expiryYYYY": "string" }'
{% endtab %}

{% tab title="Request" %}


```
{
  "cardNumber": "string",
  "cardRefId": 0,
  "expiryMM": "string",
  "expiryYYYY": "string"
}
```
{% endtab %}

{% tab title="Response" %}
​200 -> Card Validated Successfully&#x20;

201 -> Created&#x20;

400 -> request is empty&#x20;

401 -> Unauthorized&#x20;

403 -> Forbidden&#x20;

404 -> Not Found&#x20;

500 -> INTERNAL ERROR
{% endtab %}
{% endtabs %}
