# Subscription Init API

{% swagger method="post" path="" baseUrl="<domain>/wallet/autoTopup/v2/subscription/init" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
The Program ID got from the API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}
The Account Number got from the API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerId" required="true" %}
Account Number
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

<table><thead><tr><th width="260.5">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>WAL01</td><td>customer id is empty</td></tr><tr><td>WAL20</td><td>AutoTopup subscription Initiation failed.. Please try after some time.</td></tr><tr><td>WAL22</td><td>auto topup subscription already enabled</td></tr><tr><td>WAL21</td><td>AutoTopup subscription Initiated Successfully</td></tr></tbody></table>

### Response Detailsle

<table><thead><tr><th width="200">Response Field</th><th>Field Desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td></td><td>String</td><td></td></tr><tr><td>resDesc</td><td>SUCCESS, FAILURE status of the API</td><td>String</td><td>Variable, 5–8 characters</td></tr><tr><td>merchantId</td><td>Merchant ID</td><td>String</td><td></td></tr><tr><td>merchantName</td><td>Merchant Name</td><td>String</td><td></td></tr><tr><td>merchantTxnId</td><td>Merchant Txn Id</td><td>String</td><td></td></tr></tbody></table>



{% tabs %}
{% tab title="Sample Curl Command" %}
```json
curl --location --request POST '<domain>/wallet/autoTopup/v2/subscription/init' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=268743CC4FCDD918A01893968C83A481' \
--data-raw '{
    "customerId":"1234568374"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "customerId":"1234568374"
{
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "WAL21",
    "resDesc": "AutoTopup subscription Initiated Successfully", data={
        "merchantId": "171756421435003980",
        "merchantName": "Bankezy Wallet Card",
        "merchantTxnId": "202305290552553806nC12aF2"
    }
}
```
{% endtab %}
{% endtabs %}
