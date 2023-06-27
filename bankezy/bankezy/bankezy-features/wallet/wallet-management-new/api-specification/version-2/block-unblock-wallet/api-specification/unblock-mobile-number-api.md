---
description: This API is used to unblock the mobile number.
---

# Wallet card unblock

{% swagger method="post" path="" baseUrl="<domain>/wallet/v2/card/unblock" summary="" %}
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

{% swagger-parameter in="header" name="walletId" required="true" type="int" %}
Blocked wallet id
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

## Custom Response codes

| Response Code | Response Description                        |
| ------------- | ------------------------------------------- |
| WAL105        | Card Unblocked                              |
| WAL106        | Card UnBlock failed, unable to unblock card |

### Response Details

<table><thead><tr><th width="129">Response Field</th><th>Field Desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>response Code of the API</td><td>String</td><td></td></tr><tr><td>resDesc</td><td>response Description of the API</td><td>String</td><td>variable</td></tr></tbody></table>

{% tabs %}
{% tab title="Sample  Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/wallet/accountManagement/v1/unblockNumber' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-ACCOUNT-NUMBER: 123'
\--header 'Content-Type: text/plain'
--data-raw '{
  "walletId" : 123
}
'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "walletId" : 123
}

```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "WAL105",
    "resDesc": "Card UnBlocked"
}
```
{% endtab %}
{% endtabs %}
