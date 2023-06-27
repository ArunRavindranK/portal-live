---
description: This API helps to initiate a transaction in bankEzy
---

# Verify IVR API

{% swagger method="post" path="" baseUrl="<domain>/payments/v2/txn/verifyIVR" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="long" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="int" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="long" required="true" %}
Id number for a merchant. This will be generated at the time of merchant onboarding process
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantName" required="true" %}
name of a merchant. This will be generated at the time of merchant onboarding process
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantTxnId" required="true" %}
merchant transaction id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmt" type="long" required="true" %}
user entered transaction amount without implied decimal format
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDesc" required="true" %}
Any description for the transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" required="true" %}
Transaction type Example : IAP (InApp Payment)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recurringPayment" type="boolean" %}
This value can be true if user want to enable recurring payment 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.subscriptionDesc.subscriptionDesc" %}
If recurring payment enable. this field is mandatory. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.subscriberName.subscriberName" %}
If recurring payment enable. this field is mandatory. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.subscriberId" %}
If recurring payment enable. this field is mandatory. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.maxAmount" type="long" %}
If recurring payment enable. this field is mandatory. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.minAmount" type="long" %}
If recurring payment enable. this field is mandatory. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.variablePayment" type="boolean" %}
If recurring payment enable. this field is mandatory. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.topUpAmount" type="long" %}
If recurring payment enable. this field is mandatory. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.expiryDate" %}
If recurring payment enable. this field is mandatory. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="CardFee.creditCard" type="long" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="CardFee.debitCard" type="long" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="CardFee.prepaidCard" type="long" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="CardFee.general" type="long" %}

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
{% endswagger %}

## Custom Response codes

| Response code | Response description          |
| ------------- | ----------------------------- |
| PMT001        | Execution Failure.            |
| PMT200        | Success                       |
| PMT059        | Invalid merchant Id passed    |
| PMT057        | Invalid wibmo txn id passed!! |

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request POST 'http://localhost:2442/payments/v2/txn/verifyIVR' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=1EFD299E213DEE8847A52413CD0FB47E' \
--data-raw '{
    "wibmoTxnId":2022072210010010031,
    "merchantTxnId":"202204251412233239dW90yA8", 
    "mpiTxnId":"8050880123", 
    "skipIvr":false, 
    "otpValue":"234567", 
    "otpId":"4590917b-ea43-4616-a1de-09a30c72aff2", 
    "accountNumber":123
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "wibmoTxnId":2022072210010010031,
    "merchantTxnId":"202204251412233239dW90yA8", 
    "mpiTxnId":"8050880123", 
    "skipIvr":false, 
    "otpValue":"234567", 
    "otpId":"4590917b-ea43-4616-a1de-09a30c72aff2", 
    "accountNumber":123
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": "PMT200",
    "resDesc": "SUCCESS",
    "data": {
        "wibmoTxnId": 2022072210010010007,
        "merchantId": 171756421435003980,
        "merchantTxnId":"202204251412233239dW90yA8", 
        "txnAmt": 10000,
        "txnDate":"20230531",
        "chargeAttempted":false
}
```
{% endtab %}
{% endtabs %}
