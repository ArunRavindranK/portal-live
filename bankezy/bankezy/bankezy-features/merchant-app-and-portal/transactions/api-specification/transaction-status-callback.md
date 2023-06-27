---
description: >-
  Post the transaction status from the CBS to BankEzy. BankEzy will send the
  corresponding notification as per configuration to Merchant application.
---

# Transaction status -Callback

{% swagger method="post" path="/merchant-payments/v1/payment/cbdctran" baseUrl="<domain>" summary="Get the Transaction status" %}
{% swagger-description %}
This api will return the transaction status based on the transaction id provided.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" type="String" required="true" name="X-API-KEY" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDate" type="String" required="true" %}
Transaction date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnId" type="String" required="true" %}
Transaction id
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

{% tabs %}
{% tab title="Sample curl command" %}
```json

curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/merchant-payments/v1/txnstatus' 
--header 'X-API-KEY: MOB-APP1-1114' 
--header 'X-API-TOKEN: token' \
--header 'Content-Type: application/json' 
--data-raw '{
  "txnDate": "2022-12-05",
  "txnId": "989998"
}'

```
{% endtab %}

{% tab title="Request sample" %}
```json

{
  "txnDate": "2022-12-05",
  "txnId": "989998"
}


```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "MERP_2000",
  "resDesc": "SUCCESS",
  "data": {
    "txnAmount": "100.00",
    "txnStatus": "SUCCESS",
    "txnRef": "001j5w7Vk4cv05mUDhuLn1pY5WOYLszpEPr",
    "txnType": "PAY",
    "txnRemarks": "PAY",
    "payerName": "RIYAZ MOHAMMAD",
    "txnDate": "2022-12-05 15:57:02",
    "txnId": "001274a09b7125b46628a050015a6f283d1",
    "payerMobile": "919552548625",
    "payerVpa":"vpa",
    "payerWallet":"wallet",
    "payeeVpa":"vpa",
    "payeeWallet":"wallet",
    "merchantId":"1001"
  }
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="371">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MERP_2000</td><td>SUCCESS</td></tr><tr><td>MERP_4001</td><td>MERCHANT NOT CONFIGURED</td></tr><tr><td>MERP_5000</td><td>TRY_LATER</td></tr><tr><td>MERP_4000</td><td>TRANSACTION DECLINED</td></tr></tbody></table>

