---
description: >-
  Api Supports Transfer Money from Bankezy wallet to another wallet, convenience
  to client  just recipient mobile with other mandatory fields in API
---

# Send Money using mobile number API

{% swagger method="post" path="" baseUrl="<domain>/wallet/sendmoney/api/v2" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Int" required="true" %}
Transfer amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" type="String" required="true" %}
Product Type(wallet type ex: RW)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientMobileNo" type="String" required="true" %}
Receiver mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="remarks" type="String" required="true" %}
Any message
{% endswagger-parameter %}

{% swagger-parameter in="body" name="senderWalletId" type="Int" required="true" %}
Sender wallet ref number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Money transferred successfully!" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="Created" %}
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
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/sendmoney/api/v2'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token' --data-raw '{ "amount": 1, "productType": "RW", "recipientMobileNo": "7000000011", "remarks": "test", "senderWalletId": 13 }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "amount": 1,
  "productType": "RW",
  "recipientMobileNo": "7000000011",
  "remarks": "test",
  "senderWalletId": 13
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "money transfered successfully",
  "data": {
    "txnId": "202207251142102996rP0",
    "amount": 1,
    "availableBal": 964416,
    "senderMobileNo": "8892239811",
    "recipientMobileNo": "7000000011",
    "remarks": "test",
    "txnDate": 1658749330299
  }
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

| Response code | Response description                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ​2            | ​sender wallet card not found (or) impl id not found (or) card not found (or) Failure (or) prepaid response is null                                                                                                                                                                                                                                                                                                                          |
| 3             | internal server error                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ​26           | customer id is empty                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 37            | amount is zero                                                                                                                                                                                                                                                                                                                                                                                                                               |
| 38            | ​wallet id is zero                                                                                                                                                                                                                                                                                                                                                                                                                           |
| 150           | sender user account details not available for this mobile number (or) sender user id mismatch for this mobile number (or) The recipient is not a registered Bankezy wallet user.                                                                                                                                                                                                                                                             |
| 250           | Debit funds is disabled for this card (or) credit funds is disabled for this card                                                                                                                                                                                                                                                                                                                                                            |
| 300           | Your max amount per transaction limit is Rs %s. Please enter a smaller amount. (or) Your remaining limit is Rs %s for this month. Please enter a smaller amount. (or) Your remaining limit is Rs %s for today. Please enter a smaller amount. (or) You are not allowed any more transactions this month. Please retry next month. (or) You are not allowed any more transactions today. Please retry tomorrow. (or) KYC limits are not found |
| 350           | Recipient card number not found                                                                                                                                                                                                                                                                                                                                                                                                              |
