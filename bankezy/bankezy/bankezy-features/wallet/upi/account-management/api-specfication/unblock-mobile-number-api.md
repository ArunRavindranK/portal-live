---
description: This API is used to unblock the mobile number.
---

# Unblock Mobile Number API

{% swagger method="post" path="" baseUrl="<domain>/wallet/accountManagement/v1/block/mobileNumber" summary="" %}
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

{% tabs %}
{% tab title="Sample  Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/wallet/accountManagement/v1/unblockNumber' \
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
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": "9877506320 unblocked successfully"
}
```
{% endtab %}
{% endtabs %}
