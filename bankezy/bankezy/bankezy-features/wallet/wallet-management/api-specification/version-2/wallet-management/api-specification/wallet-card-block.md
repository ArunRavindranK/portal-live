---
description: This API can be used to block the wallet card as per request.
---

# Wallet card block

{% swagger method="post" path="" baseUrl="<domain>/wallet/v2/card/block" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
The Program ID got from the API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}
The Account Number got from the API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletId" required="true" type="int" %}
wallet id to be blocked
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

## Custom Response code

| Response Code | Response Description                    |
| ------------- | --------------------------------------- |
| WAL104        | Card Block failed, unable to block card |
| WAL103        | Card Blocked                            |

### Response Details

<table><thead><tr><th width="225">Response </th><th>Field Desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>response Code of the API</td><td>String</td><td></td></tr><tr><td>resDesc</td><td>response Description of the API</td><td>String</td><td>Variable</td></tr><tr><td>accountNumber</td><td>accountNumber of the user</td><td>String</td><td></td></tr><tr><td>blockedMobileNumber</td><td>Mobile Number (to block)</td><td>String</td><td></td></tr><tr><td>blockedUserName</td><td>User Name (to block)</td><td>String</td><td></td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy
-azure.pcdev.enstage-sas.com\wallet\v2\card\block' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-ACCOUNT-NUMBER: 423'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=268743CC4FCDD918A01893968C83A481' \
--data-raw '{
    "walletId" : 123
}'
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
    "resCode": "WAL103",
    "resDesc": "Card Blocked",
    "data": {
        "accountNumber": "423",
        "blockedMobileNumber": "7827737375",
        "blockedUserName": "Bal"
    }
}
```
{% endtab %}
{% endtabs %}
