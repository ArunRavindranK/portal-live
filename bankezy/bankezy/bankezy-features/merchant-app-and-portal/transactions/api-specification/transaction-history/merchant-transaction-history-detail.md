---
description: Get the detailed information of the transaction
---

# Merchant Transaction History - Detail

{% swagger method="post" path="/txnHistory/v1/merchanttxndetail" baseUrl="<domain>" summary="Merchant Transaction History Details" %}
{% swagger-description %}
This is to fetch the merchant txn history details for the given transaction ref id.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnRef" type="String" required="true" %}
Transaction ref number
{% endswagger-parameter %}

{% swagger-parameter in="body" required="false" name="txnId" type="String" %}
Transaction id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="List<String>" %}
Transaction type

eg: PAY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnStatus" type="List<String>" %}
transaction status

eg: SUCCESS , FAILED etc..
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
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/txnHistory/v1/merchanttxndetail' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'Content-Type: application/json' \
--data-raw '{
    "txnRef":"001j5w7Vk4cv05mUDhuLn1pY5WOYLszpEPr",
    "txnStatus": ["PAID","SUCCESS"]
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json

{
    "txnRef":"001j5w7Vk4cv05mUDhuLn1pY5WOYLszpEPr",
    "txnStatus": ["SUCCESS","FAILED"],
    "txnId":"2023025262723093"
}


```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "TXNM_2000",
    "resDesc": "SUCCESS",
    "data": {
        "txnType": "PAY",
        "txnRemarks": "PAY",
        "txnAmount": 200.0,
        "txnDate": 1674604800000,
        "txnId": "2023025262723093",
        "txnRef": "001j5w7Vk4cv05mUDhuLn1pY5WOYLszpEPr",
        "txnStatus": "SUCCESS",
        "merchantRc": "00",
        "payerName": "Shailendra",
        "payerMobile": "919552548625",
        "merCategory": null,
        "merchantMid": "1004",
        "merchantVpa": "merchant1@vpa",
        "merchantName": "sachin",
        "merchantWallet": "cbdc wallet",
        "merchantMobile": "8888154083",
        "merchantMcc": "1234",
        "merchantAcctNum": null,
        "payerAcctNum": null,
        "payerVpa": "merchant1@vpa",
        "payerWallet": "cbdc wallet",
        "txnShortDesc": null,
        "payerRc": "00"
    }
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>TXNM_2000</td><td>SUCCESS</td></tr><tr><td>TXNM_4001</td><td>TRANSACTION_DETAILS_NOT_AVAILABLE</td></tr><tr><td>TXNM_5000</td><td>TRY_LATER</td></tr></tbody></table>

