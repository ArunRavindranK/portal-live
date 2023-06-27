---
description: This API is used to unblock the mobile number.
---

# Unblock Mobile Number API

{% swagger method="post" path="" baseUrl="<domain>/wallet/accountManagement/v2/unblockNumber" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
Program ID got from the API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}
Account Number got from the API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="accountNumber" required="true" %}
Account Number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="blockedMobileNumber" required="true" %}
Blocked Mobile Number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="blockedUserName" required="true" %}
Blocked User Name
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
{% endswagger %}

| Response Code | Response Desc |
| ------------- | ------------- |
| WAL200        | Success       |
| WAL100        | Failure       |
|               |               |

### Response Details

<table><thead><tr><th width="132">Response Field</th><th>Field Desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>rescode</td><td>response Code of the API</td><td>String</td><td></td></tr><tr><td>resdesc</td><td>response Description of the API</td><td>String</td><td></td></tr><tr><td>data</td><td>It will contain the String describing the response of API</td><td>Object</td><td></td></tr></tbody></table>



{% tabs %}
{% tab title="Sample  Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/wallet/accountManagement/v2/unblockNumber' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-ACCOUNT-NUMBER: 123'
\--header 'Content-Type: text/plain'
--data-raw '{
  "blockedMobileNumber" : "9877506320"
}
'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "blockedMobileNumber" : "9877506320" 
}

```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "WAL200",
    "resDesc": "SUCCESS",
    "data": "9877506320 unblocked successfully"
}
```
{% endtab %}
{% endtabs %}
