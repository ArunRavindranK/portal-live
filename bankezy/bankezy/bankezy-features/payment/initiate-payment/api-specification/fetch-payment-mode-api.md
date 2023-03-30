---
description: >-
  This API helps to returns list of payment mode like linked card, wallet card
  supported by the program
---

# Fetch Payment Mode API

{% swagger method="get" path="" baseUrl="<domain>/payments/mode/v1" summary="" %}
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

{% swagger-parameter in="body" name="supportedPaymentMode" required="false" %}
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

{% tabs %}
{% tab title="Sample Curl Request" %}
```
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
```json
{
    "resCode": 200,
    "resDesc": "Account(s) fetched Successfully",
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
```
{% endtab %}
{% endtabs %}
