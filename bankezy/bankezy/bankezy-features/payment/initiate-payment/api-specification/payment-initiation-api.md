---
description: This API helps to initiate a transaction in bankEzy
---

# Payment Initiation API

{% swagger method="get" path="" baseUrl="<domain>/payments/txn/init/v1" summary="" %}
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

{% swagger-parameter in="body" name="recurringPayment" type="boolean" required="false" %}
This value can be true if user want to enable recurring payment
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.subscriptionDesc" required="false" %}
If recurring payment enable. this field is mandatory.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.subscriberName" required="false" %}
If recurring payment enable. this field is mandatory.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.subscriberId" required="false" %}
If recurring payment enable. this field is mandatory.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.maxAmount" type="long" required="false" %}
If recurring payment enable. this field is mandatory.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.minAmount" type="long" required="false" %}
If recurring payment enable. this field is mandatory.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.variablePayment" type="boolean" required="false" %}
If recurring payment enable. this field is mandatory.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.topUpAmount" type="long" required="false" %}
If recurring payment enable. this field is mandatory.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.expiryDate" required="false" %}
If recurring payment enable. this field is mandatory.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="CardFee.creditCard" type="long" required="false" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="CardFee.debitCard" type="long" required="false" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="CardFee.prepaidCard" type="long" required="false" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="CardFee.general" type="long" required="false" %}

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

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request POST 'http://localhost:2442/payments/txn/init/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=1EFD299E213DEE8847A52413CD0FB47E' \
--data-raw '{
    "countryCode":"91", 
    "merchantId":"171756421435003980", 
    "merchantName":"Load Money. Merchant", 
    "merchantTxnId":"202204251412233239dW90yA8", 
    "mobile":"8050880123", 
    "recurringPayment":"false", 
    "txnAmt":"10000", 
    "txnDesc":"LoadMoney", 
    "txnType":"LoadMoney"
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "countryCode":"91", 
    "merchantId":"171756421435003980", 
    "merchantName":"Load Money. Merchant", 
    "merchantTxnId":"202204251412233239dW90yA8", 
    "mobile":"8050880123", 
    "recurringPayment":"false", 
    "txnAmt":"10000", 
    "txnDesc":"LoadMoney", 
    "txnType":"LoadMoney"
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "merchantId": 171756421435003980,
        "merchantName": "Load Money. Merchant",
        "merchantTxnId": "202204251412233239dW90yA8",
        "merchantReturnUrl": "https://api1.pcdev.enstage-sas.com/merchant/redirectFromPG",
        "txnAmt": 10000,
        "txnDesc": "LoadMoney",
        "txnFormattedAmount": "Rs. 100.00",
        "wibmoTxnId": 2022072210010010007,
        "recurringPaymentRefId": 0,
        "supportedPaymentType": [
            "LC,UPI,NB,UPII,RP"
        ],
        "restrictedPaymentType": [
            "w.ds.pt.none"
        ],
        "cardFee": null
    }
}
```
{% endtab %}
{% endtabs %}