# Subscription Confirm API

{% swagger method="post" path="" baseUrl="<domain>/wallet/autoTopup/v2/authStatus/update" summary="" %}
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

<table><thead><tr><th width="260.5">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>WAL05</td><td>opup amount should not be lessthan or equal to zero</td></tr><tr><td>WAL06</td><td>threshold amount should not be lessthan or equal to zero</td></tr><tr><td>WAL149</td><td>authentication is empty</td></tr><tr><td>WAL150</td><td>txn date is empty</td></tr><tr><td>WAL09</td><td>topup amount should be grater than the threshold amount</td></tr><tr><td>WAL148</td><td>Txn Details not found.. Please try with valid details</td></tr><tr><td>WAL151</td><td>Authentication Failed or Authorization Failed</td></tr><tr><td>WAL152</td><td>autotopup subscribed successfully</td></tr></tbody></table>

### Response Details

<table><thead><tr><th width="122">Response Field</th><th>Field Desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>response Code of the API</td><td>String</td><td></td></tr><tr><td>resDesc</td><td>response Description of the API</td><td>String</td><td>Variable, 5–8 characters</td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Curl Command" %}
```json
curl --location --request POST '<domain>/wallet/autoTopup/v2/authStatus/update'
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=268743CC4FCDD918A01893968C83A481' \
--data-raw '{
    "thresholdAmt": 100,
    "topupAmt": 50000,
    "merchnatTxnId":"171756421435003985",
    "wibmoTxnId":"202305290552553806nC12aF2",
    "chargeAttempted":"true",
    "authentication":true,
    "txnDate":"20230529",
    "recurringPaymentRefId":20230529055254920343444
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "thresholdAmt": 100,
    "topupAmt": 50000,
    "merchnatTxnId":"171756421435003985",
    "wibmoTxnId":"202305290552553806nC12aF2",
    "chargeAttempted":"true",
    "authentication":true,
    "txnDate":"20230529",
    "recurringPaymentRefId":20230529055254920343444
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": "WAL152",
    "resDesc": "autotopup subscribed successfully"
}
```
{% endtab %}
{% endtabs %}
