---
description: This API helps to initiate a transaction in bankEzy
---

# Payment Initiation API

{% swagger method="post" path="" baseUrl="<domain>/payments/v2/txn/init/" summary="" %}
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

| Response Field        | Field Description                                                                           | Data type     |
| --------------------- | ------------------------------------------------------------------------------------------- | ------------- |
| merchantId            | Id number for a merchant. This will be generated at the time of merchant onboarding process | long          |
| merchantName          | name of a merchant. This will be generated at the time of merchant onboarding process       | String        |
| merchantTxnId         | merchant transaction id                                                                     | String        |
| txnAmt                | user entered transaction amount without implied decimal format                              | long          |
| txnDesc               | Any description for the transaction                                                         | String        |
| txnFormattedAmount    | transaction amount with Rupee                                                               | String        |
| wibmoTxnId            | Unique transaction id                                                                       | long          |
| recurringPaymentRefId | transaction id if recurring payment enabled                                                 | Integer       |
| supportedPaymentType  | String array of supported payment mode LC, WC, UPI, NB                                      | List\<String> |
| restrictedPaymentType | payment type that is restricted in a list                                                   | List\<String> |
| cardFee               |                                                                                             | CardFee       |

#### Custom Response Code

| Response code | Response Description |
| ------------- | -------------------- |
| PMT001        | Execution Failure    |
| PMT200        | SUCCESS              |
| PMT004        | Invalid merchant Id  |

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request POST 'http://localhost:2442/payments/v2/txn/init' \
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
<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "countryCode":"91", 
    "merchantId":"171756421435003980", 
    "merchantName":"Load Money. Merchant", 
    "merchantTxnId":"202204251412233239dW90yA8", 
    "mobile":"8050880123", 
    "recurringPayment":"false", 
    "txnAmt":"10000", 
    "txnDesc":"LoadMoney", 
    "txnType":"LoadMoney"
}
</code></pre>
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
