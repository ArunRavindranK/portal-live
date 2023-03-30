---
description: >-
  Api to Update Auto Top Subscription details like threshold amount, topup
  amount, source card change or active/inactive the subscription
---

# Update Auto Top Subscription API

{% swagger method="post" path="" baseUrl="<domain>/wallet/internal/updatesubscription/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="durationForConsecutiveDebits" type="Int" required="true" %}
​Duration For Consecutive Debits
{% endswagger-parameter %}

{% swagger-parameter in="body" name="expiryDate" type="String" required="true" %}
Expiry Date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="maxAmount" type="Int" required="true" %}
Max Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" required="true" %}
Merchant Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="minAmount" type="Int" required="true" %}
​Min Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nickName" type="String" required="true" %}
Nick Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recurringPaymentRefId" type="Int" required="true" %}
​Recurring Payment Ref Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="String" required="true" %}
Status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="topUpAmount" type="Int" required="true" %}
TopUp Amount
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userId" type="Int" required="true" %}
user Id
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

| Response code | Response description                                 |
| ------------- | ---------------------------------------------------- |
| ​69           | topup amount should not be lessthan or equal to zero |
| ​80           | ​merchant Id is Mandatory                            |
| 83            | User Id Should be Greater than Zero                  |
| 84            | Subscription Status Should be Greater than Zero      |
| 100           | update Subscription Failed..                         |

{% tabs %}
{% tab title="Sample curl command" %}
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/internal/updatesubscription/v1'

\\--header 'Content-Type: text/plain'

```
\--header 'X-API-KEY: MOB-APP-2001'
```

\\--header 'X-API-TOKEN:token' --data-raw '{ "durationForConsecutiveDebits": 0, "expiryDate": "2022-05-27T12:35:58.810Z", "maxAmount": 0, "merchantId": "string", "minAmount": 0, "nickName": "string", "recurringPaymentRefId": 0, "status": "Action code will be '1' or '0' or '2'. 1 = Enable Auto Pay, '0' =Disable/Remove/Delete Auto Pay '2' = Pause Auto Pay", "topUpAmount": 0, "userId": 0 }'​
{% endtab %}

{% tab title="Request" %}
```
{
  "durationForConsecutiveDebits": 0,
  "expiryDate": "2022-06-02T16:52:41.761Z",
  "maxAmount": 0,
  "merchantId": "string",
  "minAmount": 0,
  "nickName": "string",
  "recurringPaymentRefId": 0,
  "status": "Action code will be '1' or '0' or '2'. 1 = Enable Auto Pay, '0' =Disable/Remove/Delete Auto Pay '2' = Pause Auto Pay",
  "topUpAmount": 0,
  "userId": 0
}
```
{% endtab %}

{% tab title="Response" %}
200 -> Subscription updated Successfully..

201 -> Created

400 -> request is empty

401 -> Unauthorized

403 -> Forbidden

404 -> Not Found

500 -> INTERNAL ERROR
{% endtab %}
{% endtabs %}
