# Send Money API

{% swagger method="post" path="" baseUrl="http://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/v2/sendMoney" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceFingerprint" required="false" %}
deviceFingerprint
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVpa" %}
payer Vpa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVpa" required="true" %}
payee Vpa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" required="true" %}
payee Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" required="true" %}
amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="upiRequestId" required="false" %}
upiRequestId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankAccountUniqueId" required="false" %}
bank Account UniqueId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="remarks" %}
remarks
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currency" %}
currency
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transacType" required="true" %}
transacion Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amountBlocked" required="true" %}
amount Blocked
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refUrl" required="false" %}
reference Url
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refCategory" %}
reference Category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mcc" %}
merchant category code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transacationReference" %}
transacation Reference
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParameters" required="false" %}
user definded field
{% endswagger-parameter %}

{% swagger-parameter in="body" name="originalTxnId" required="true" %}
original transaction id
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

## Custom response codes

| Response code | Response description               |
| ------------- | ---------------------------------- |
| UPI35         | No linked account for this account |
| UPI36         | Send money failed                  |
| UPI37         | Transaction is in pending state    |

```postman_json
txnDate
```

{% tabs %}
{% tab title="Sample CURL request" %}
```
curl --location 'http://bankezy-azure.pcdev.
enstage-sas.com/upi-integration/upi/transaction/v2/sendMoney' \
--header 'x-program-id: 2001' \
--header 'x-account-number: 3199' \
--header 'Content-Type: application/json' \
--data-raw '{
    "deviceFingerprint" : "",
    "payerVpa" : "9620686057.bankezy@payu",
    "payeeVpa" : "918296364009.bankezy@payu",
    "payeeName" : "",
    "amount" : "100",
    "upiRequestId" : "",
    "bankAccountUniqueId" : "89",
    "remarks" : "",
    "currency" :"INR",
    "transacType" : "P2P_PAY",
    "isAmountBlocked" : "90438cddc696b80d1559c8d754b6088ae82ff45b170e46e569a4870ac1da9060",
    "refUrl" : "https://www.juspay.com/",
    "refCategory" :"",
    "mcc" : "",
    "transacationReference" : "",
    "udfParameters" :"",
    "originalTxnId" : "202207110910298029hQ36zM2"
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "deviceFingerprint" : "",
    "payerVpa" : "9620686057.bankezy@payu",
    "payeeVpa" : "918296364009.bankezy@payu",
    "payeeName" : "",
    "amount" : "100",
    "upiRequestId" : "",
    "bankAccountUniqueId" : "89",
    "remarks" : "",
    "currency" :"INR",
    "transacType" : "P2P_PAY",
    "isAmountBlocked" : "90438cddc696b80d1559c8d754b6088ae82ff45b170e46e569a4870ac1da9060",
    "refUrl" : "https://www.juspay.com/",
    "refCategory" :"",
    "mcc" : "",
    "transacationReference" : "",
    "udfParameters" :"",
    "originalTxnId" : "202207110910298029hQ36zM2"
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
  "status": "SUCCESS",
  "responseCode": "UPI200",
  "responseMessage": "SUCCESS",
  "payload": {
    "merchantId": "TEST",
    "merchantChannelId": "TESTAPP",
    "merchantCustomerId": "test-merchantcustomer-1",
    "merchantRequestId": "redId1234",
    "customerMobileNumber": "919988776655",
    "payerVpa": "customervpa@bank",
    "payeeMcc": "0000",
    "payeeMerchantCustomerId": "DEMO-CUST-5678",
    "payeeName": "John Doe",
    "payeeVpa": "payee@xyz",
    "refUrl": "https://www.abcxyz.com/",
    "bankAccountUniqueId": "fb96f8b2b1ab0c070d0d894fd2e577a3d6129882c874e3700505eebfb8070",
    "bankCode": "123456",
    "maskedAccountNumber": "XXXX123456",
    "amount": "2.00",
    "transactionType": "INTENT_PAY",
    "transactionTimestamp": "2017-06-09T17:57:49+05:30",
    "gatewayTransactionId": "AUTef1a2908395239df56663244f8c7deaa",
    "gatewayReferenceId": "809323430413",
    "gatewayResponseStatus": "SUCCESS",
    "gatewayResponseCode": "00",
    "gatewayResponseMessage": "Your transaction is successful"
  },
  "udfParameters": "{}"
}
```
{% endtab %}
{% endtabs %}
