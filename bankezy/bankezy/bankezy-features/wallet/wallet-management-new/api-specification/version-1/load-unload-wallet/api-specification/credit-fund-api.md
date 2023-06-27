---
description: Credit funds into wallet
---

# Credit Fund API



{% swagger method="post" path="" baseUrl="<domain>/wallet/credit/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="Int" required="true" %}
amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryName" type="String" required="true" %}
Beneficiary Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mcc" type="String" required="true" %}
mcc
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="Int" required="true" %}
Merchant Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="originalRRN" type="String" required="true" %}
original RRN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="rrn" type="String" required="true" %}
​rrn
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="String" required="true" %}
txn Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" type="Int" required="true" %}
walletId
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" %}
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

## Custom response code

| Response code | Response description                                                                                                                                               |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1             | Funds credited successfully                                                                                                                                        |
| ​2            | Invalid wallet Id Passed (or) credit funds is disabled for this cardimpl id not found (or) prepaid card details is null (or) Failure (or) prepaid response is null |
| ​3            | Internal server error                                                                                                                                              |
| ​20           | Request is empty                                                                                                                                                   |
| 26            | ​Customer id is empty                                                                                                                                              |
| 35            | ​mcc is empty                                                                                                                                                      |
| 36            | ​rrn is empty                                                                                                                                                      |
| ​37           | Amount is zero                                                                                                                                                     |
| 38            | Wallet id is zero                                                                                                                                                  |
| ​101          | Txn type is empty                                                                                                                                                  |



{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/credit/api/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token'
--data-raw '{ "amount": 0, "beneficiaryName": "string", "mcc": "string", "merchantId": "string", "originalRRN": "string", "rrn": "string", "txnType": "Load Money", "walletId": 0 }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}


```json
{
  "amount": 0,
  "beneficiaryName": "string",
  "mcc": "string",
  "merchantId": "string",
  "originalRRN": "string",
  "rrn": "string",
  "txnType": "Load Money",
  "walletId": 0
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 1,
  "resDesc": "funds credited successfully",
  "data": {
    "custId": "29",
    "walletId": 13,
    "refNumber": "5164937",
    "amount": 200,
    "availableBal": 964217,
    "remarks": "Card Recharge",
    "ppTxnId": "1962028"
  }
}
```
{% endtab %}
{% endtabs %}
