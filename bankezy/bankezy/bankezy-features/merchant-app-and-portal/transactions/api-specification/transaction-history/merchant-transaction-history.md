---
description: Get the Merchant transaction history
---

# Merchant Transaction History

{% swagger method="post" path="/txnHistory/v1/merchanttxn" baseUrl="<domain>" summary="Merchant Transaction history" %}
{% swagger-description %}
This is to fetch the merchant txn history from start date to end date.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" type="String" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fromDate" required="true" type="String" %}
fromDate to fetch merchant transaction history
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="toDate" required="true" type="String" %}
toDate to fetch merchant transaction history
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="List<String>" %}
transaction type

eg: PAY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnStatus" type="List<String>" %}
transaction status

eg: SUCCESS , FAILED etc..
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnId" type="String" %}
transaction id
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

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/txnHistory/v1/merchanttxn' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fromDate":"2022-12-05 00:00:00",
    "toDate":"2022-12-11 00:00:00"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json

{
    "fromDate":"2022-12-05 00:00:00",
    "toDate":"2022-12-11 00:00:00"
}

```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "TXNM_2000",
    "resDesc": "SUCCESS",
    "data": [
        {
            "txnType": "PAY",
            "txnRemarks": "PAY",
            "txnAmount": 1200.0,
            "txnDate": 1674000000000,
            "txnId": "2023018256245658",
            "txnRef": "001j5w7Vk4cv05mUDhuLn1pY5WOYLszpEPr",
            "txnStatus": "SUCCESS",
            "merchantRc": "00",
            "payerName": "Shailendra",
            "payerMobile": "919552548625",
            "payerRc": "00"
        },
        {
            "txnType": "PAY",
            "txnRemarks": "PAY",
            "txnAmount": 2100.0,
            "txnDate": 1674000000000,
            "txnId": "2023018195426727",
            "txnRef": "001j5w7Vk4cv05mUDhuLn1pY5WOYLszpEPr",
            "txnStatus": "SUCCESS",
            "merchantRc": "00",
            "payerName": "Shailendra",
            "payerMobile": "919552548625",
            "payerRc": "00"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>TXNM_2000</td><td>SUCCESS</td></tr><tr><td>TXNM_4001</td><td>TRANSACTION_DETAILS_NOT_AVAILABLE</td></tr><tr><td>TXNM_5000</td><td>TRY_LATER</td></tr></tbody></table>
