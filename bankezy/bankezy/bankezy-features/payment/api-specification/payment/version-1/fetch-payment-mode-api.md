---
description: >-
  This API helps to returns list of payment mode like linked card, wallet card
  supported by the program
---

# Fetch Payment Mode API

{% swagger method="post" path="" baseUrl="<domain>/payments/mode/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="long" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-api-key" required="true" type="int" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerId" type="long" required="false" %}
Account number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="int" required="false" %}
Saved card identification number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lcGrouping" type="boolean " required="false" %}
If grouping is required this needs to be enabled
{% endswagger-parameter %}

{% swagger-parameter in="body" name="supportedPaymentMode" %}
String array of supported payment mode LC, WC, UPI, NB
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

## Response Details

| Response Field            | Field Description                                                                                             | Data Type |
| ------------------------- | ------------------------------------------------------------------------------------------------------------- | --------- |
| wallets.customerId        | Customer id                                                                                                   | String    |
| wallets.name              | Name of the customer                                                                                          | String    |
| wallets.walletId          | Customer id at prepaid end                                                                                    | Integer   |
| wallets.mobile            | Customer mobile number that will be linked at prepaid                                                         | String    |
| wallets.cardMask          | Masked wallet card number                                                                                     | String    |
| wallets.balancec          | Wallet balace will be represented in implied decimal                                                          | Integer   |
| wallet.status             | Active or Inactive string will be retured                                                                     | String    |
| wallets.productType       | Type of wallet Eg.Regular wallet(RW) or one time wallet (OT)                                                  | String    |
| wallets.txnProfile.status | Status of the transaction type allowed or not                                                                 | Boolean   |
| wallets.txnProfile.type   | Type of transaction                                                                                           | String    |
| specificIntentEnabled     | If this value is false then payment apps from the user's mobile will be listed down for UPI based transaction | Boolean   |
| specificApps.appName      | Name of the payment app                                                                                       | String    |
| specificApps.appPriority  | Priority level of app to view it to the user                                                                  | int       |
| specificApps.appPackage   | Used for Android to open the app                                                                              | String    |
| specificApps.appURL       | Used for IOS to open the app                                                                                  | String    |

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request POST 'http://localhost:2442/payments/mode/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=39ABD7D35400DEBCE867CB38AD2F9DFD' \
--data-raw '{
    "customerId": "2928",
    "supportedPaymentMode": "WC"
}'
```
{% endtab %}

{% tab title="Sample Request" %}
```json
{
    "customerId": "2928",
    "supportedPaymentMode": "WC"
}
```
{% endtab %}

{% tab title="Sample Response" %}
<pre class="language-json"><code class="lang-json"><strong>{
</strong>    "resCode": "PMT200",
    "resDesc": "Success",
    "data": {
        "wallets": [
            {
                "customerId": "2928",
                "name": "Nithya Kaimal",
                "walletId": 608,
                "mobile": "7466655915",
                "cardMask": null,
                "balance": 36599,
                "walletStatus": "Active",
                "productType": "RW",
                "txnProfile": [
                    {
                        "status": true,
                        "type": "e-Com"
                    }
                ]
            }
        ],
        "specificApps": null,
        "specificIntentEnabled": false
    }
}
</code></pre>
{% endtab %}
{% endtabs %}
