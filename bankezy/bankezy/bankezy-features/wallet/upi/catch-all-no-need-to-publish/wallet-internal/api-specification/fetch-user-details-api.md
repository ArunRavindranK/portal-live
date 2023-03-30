---
description: Fetch user Details like mobile, email and kyc level information
---

# Fetch user Details API



{% swagger method="get" path="" baseUrl="<domain>/wallet/internal/fetch/user/{customerId}/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
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

| Response code | Response description |
| ------------- | -------------------- |
| 100           | Card Not found       |

| <p><br>Card Validated Successfully</p> |
| -------------------------------------- |

{% tabs %}
{% tab title="Sample curl command" %}
curl --location --request GET 'https://payment1.pcdev.enstage-sas.com/wallet/internal/fetch/user/{customerId}/v1'

\\--header 'Content-Type: text/plain'

\\--header 'X-API-KEY: MOB-APP-2001'

\\--header 'X-API-TOKEN:token'

curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/internal/updatesubscription/v1' --header 'Content-Type: application/json' --header 'X-API-TOKEN:replace\_with\_basic\_auth\_to\_be\_built\_by\_client' --data-raw '{ "durationForConsecutiveDebits": 0, "expiryDate": "2022-05-27T12:35:58.810Z", "maxAmount": 0, "merchantId": "string", "minAmount": 0, "nickName": "string", "recurringPaymentRefId": 0, "status": "Action code will be '1' or '0' or '2'. 1 = Enable Auto Pay, '0' =Disable/Remove/Delete Auto Pay '2' = Pause Auto Pay", "topUpAmount": 0, "userId": 0 }'​
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
​200 -> Card Validated Successfully&#x20;

201 -> Created&#x20;

400 -> request is empty&#x20;

401 -> Unauthorized&#x20;

403 -> Forbidden&#x20;

404 -> Not Found&#x20;

500 -> INTERNAL ERROR
{% endtab %}
{% endtabs %}
