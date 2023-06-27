---
description: This API can be used to block the mobile number  as per request.
---

# Block Mobile Number API

{% swagger method="post" path="" baseUrl="<domain>/wallet/accountManagement/v1/block/mobileNumber" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
The Program ID got from the API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}
The Account Number got from the API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountNumber" required="true" %}
Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="blockedMobileNumber" required="true" %}
Mobile Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="blockedUserName" required="true" %}
User Name
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
{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/wallet/accountManagement/v1/block/mobileNumber' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-ACCOUNT-NUMBER: 423'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=268743CC4FCDD918A01893968C83A481' \
--data-raw '{
    "blockedMobileNumber" : "7827737375",
    "blockedUserName" : "Sumit kumar"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "blockedMobileNumber" : "7827737375",
    "blockedUserName" : "Sumit kumar"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "accountNumber": "423",
        "blockedMobileNumber": "7827737375",
        "blockedUserName": "Bal"
    }
}
```
{% endtab %}
{% endtabs %}
