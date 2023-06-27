---
description: Validate user is eligible for doing a wallet to account transaction
---

# W2A Send Money API

This Api is used to identify the beneficiary cooling period, based on that beneficiary limits will be calculated. Source side transaction count and amount limit validation also will be calculated. Once amount limit validation has done, Fee and GST will be calculated.

{% swagger method="post" path="" baseUrl="<domain>/wallet/v2/transaction/sendMoney" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="long" required="true" %}
​Transaction amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="String" required="false" %}
Any transaction description
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currency" type="String" required="false" %}
Transaction currency code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionType" type="String" required="true" %}
​Transaction type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientMobileNo" type="String" required="false" %}
Receiver mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryAccountNumber" type="String" required="false" %}
Receiver account number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ifsc" type="String" required="false" %}
Receiver bank IFSC Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryName" type="String" required="false" %}
Receiver name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryId" required="false" %}
Receiver unique id from the system
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sendervpa" required="false" %}
Sender VPA
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientvpa" required="false" %}
Receiver VPA
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refCategory" required="false" %}
Reference category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refUrl" required="false" %}
Reference URL
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionReference" required="false" %}
Unique transaction reference number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="senderWalletId" required="true" type="int" %}
Sender Wallet Id from the system
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productType" required="true" %}
Wallet product type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mcc" required="false" %}
merchant category code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="upiRequestId" required="false" %}
UPI transaction request id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParams" type="Map<String, String>" required="false" %}
User definded field
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

## Custom response codes

<table><thead><tr><th width="276.5">Code</th><th>Description</th></tr></thead><tbody><tr><td>WALL300</td><td>Cooling Breached</td></tr><tr><td>​WALL102</td><td>User cannot initiate transaction. Please upgrade to full KYC</td></tr><tr><td>WALL112</td><td>​SENDER - CARD TEMPORARY BLOCK</td></tr><tr><td>WALL113</td><td>RECEIVER - CARD TEMPORARY BLOCK</td></tr><tr><td>​WALL114</td><td>​mobile# is empty</td></tr><tr><td>WALL115</td><td>Please enter an amount greater than %s</td></tr><tr><td>WALL57</td><td>wallet id is zero</td></tr><tr><td>WALL116</td><td>sender user account details not available for this mobile number</td></tr><tr><td>WALL117</td><td>sender wallet card not found</td></tr><tr><td>WALL118</td><td>The recipient is not a registered BankEzy wallet user</td></tr><tr><td>WALL119</td><td>receiver wallet card not found</td></tr><tr><td>WALL120</td><td>credit funds is disabled for this card</td></tr><tr><td>WALL121</td><td>impl id not found</td></tr><tr><td>WALL122</td><td>Your max amount per transaction limit is Rs %s. Please enter a smaller amount.</td></tr><tr><td>WALL123</td><td>KYC limits are not found</td></tr><tr><td>WALL124</td><td>You are not allowed any more transactions this month. Please retry next month.</td></tr><tr><td>WALL125</td><td>Your remaining limit is Rs %s for this month. Please enter a smaller amount.</td></tr><tr><td>WALL126</td><td>You are not allowed any more transactions today. Please retry tomorrow.</td></tr><tr><td>WALL127</td><td>Your remaining limit is Rs %s for today. Please enter a smaller amount.</td></tr><tr><td>WAL191</td><td>Payment Success</td></tr><tr><td>WAL192</td><td>money transferred successfully!</td></tr><tr><td>WAL196</td><td>Transaction initiated successfully</td></tr><tr><td>WAL197</td><td>Failed to credit the funds to destination, Please try again.</td></tr><tr><td>WAL198</td><td>Failed to debit the funds from Wallet, Please try again.</td></tr><tr><td>WAL199</td><td>Transaction initiation failed, Please try again.</td></tr></tbody></table>

{% tabs %}
{% tab title="Sample curl command" %}
````json
curl --location --request POST 'http://localhost:8912/orchestrate/v2/validation' \
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain' \
--data-raw '```postman_json
{
    "amount": 1000,
    "description": "",
    "transactionType": "W2W",
    "recipientMobileNo": "9042179396",
    "senderWalletId": 600015
'
````
{% endtab %}

{% tab title="Request sample" %}
<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "recipientvpa": "prady22@upi",
    "refURL": "https://npci.org.in",
    "senderWalletId": 600030,
    "amount": 100,
    "transactionReference": "bivek123456789012345678901234512205",
    "currency": 356,
    "beneficiaryName": "Bharat Stores",
    "transactionType": "SCAN_PAY"
}
</code></pre>
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "200",
    "resDesc": "money transferred successfully!",
    "data": {
        "txnId": "202305290818554767lL3",
        "amount": "1000",
        "availableBal": "715970",
        "senderMobileNo": "9566115998",
        "recipientMobileNo": "9042179396",
        "remarks": "SUCCESS",
        "recipientTxnId": "202305290818554765uF1",
        "txnDate": "1685348335476",
        "recipientAccosaRefNo": "1519579",
        "transactionType": "W2W"
    }
}
```
{% endtab %}
{% endtabs %}
