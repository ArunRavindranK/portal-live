---
description: Get the transaction status
---

# Get Transaction Status

{% swagger method="post" path="/payments/v1/qrinfo" baseUrl="<domain>" summary="Get the transaction status " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnId" type="String" required="true" %}
Transaction Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmount" type="String" required="true" %}
Transaction amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDate" type="String" required="true" %}
Transaction date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mid" type="String" required="true" %}
Mid
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN " type="String" required="true" %}
The token got from the login API
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
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/payments/v1/qrinfo' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'X-API-TOKEN: token' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=FA8665A348AC9F06EAD159DA259BB58F' \
--data-raw '{
    "txnId":"2022020271404400",
    "txnAmount":600,
    "txnDate":"13-01-23",
    "mid":"1002"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "txnId":"2022020271404400",
    "txnAmount":600,
    "txnDate":"13-01-23",
    "mid":"1002"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{    "resCode": "QR_200",    "resDesc": "Success"}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>QR_200</td><td>SUCCESS</td></tr><tr><td>QR_402</td><td>INVALID_TXNID</td></tr></tbody></table>

## &#x20;
