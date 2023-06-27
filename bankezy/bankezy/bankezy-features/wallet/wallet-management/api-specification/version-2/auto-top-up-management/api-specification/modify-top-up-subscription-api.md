# Modify Top-up Subscription API

{% swagger method="post" path="" baseUrl="<domain>/wallet/autoTopup/v2/modifysubscription" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
The Program ID got from the API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}
The Account Number got from the API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" required="true" type="int" %}
country code
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

<table><thead><tr><th width="260.5">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>WAL05</td><td>topup amount should not be lessthan or equal to zero</td></tr><tr><td>WAL06</td><td>threshold amount should not be lessthan or equal to zero</td></tr><tr><td>WALL09</td><td>topup amount should be grater than the threshold amount</td></tr><tr><td>WALL016</td><td>Payment Ref Id Should be Greater than Zero</td></tr><tr><td>WALL017</td><td>Subscription Status is Mandatory</td></tr><tr><td>WALL018</td><td>update Subscription Failed..</td></tr><tr><td>WALL015</td><td>merchant Id is Mandatory</td></tr></tbody></table>

### Response Details

<table><thead><tr><th width="157">Response Field</th><th>Field Desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>response Code of the API</td><td>String</td><td></td></tr><tr><td>resDesc</td><td>response Desc of the API</td><td>String</td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample CURL request" %}
```json
curl --location '<domain>/wallet/autoTopup/v2/modifysubscription' \
--header 'X-API-KEY: MOB-APP' \
--header 'X-API-TOKEN: replace-with-proper-token' \
--header 'Content-Type: application/json' \
--data '{
    "thresholdAmt": 100,
    "topupAmt": 50000,
    "merchnatId":"171756421435003985",
    "status":"A",
    "recurringPaymentRefId":20230529055254920343444
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
    "topupAmt": 50000,
    "merchnatId":"171756421435003985",
    "status":"A",
    "recurringPaymentRefId":20230529055254920343444
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": "WALL019",
    "resDesc": "Subscription updated Successfully.."
}
```
{% endtab %}
{% endtabs %}
