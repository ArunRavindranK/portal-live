---
description: This API is used to get the list of blocked mobile number
---

# Blocked Mobile Number List API

{% swagger method="post" path="" baseUrl="<domain>/wallet/accountManagement/v1/blockedlist" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
Program ID 
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}
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

{% tabs %}
{% tab title="Sample  Curl Command" %}
```json
curl --location --request GET 'https://bankezy-azure.pcdev.enstage-sas.com/wallet/accountManagement/v1/blockedlist' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-ACCOUNT-NUMBER: 123'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=268743CC4FCDD918A01893968C83A481' \
--data-raw '{
    "accountNumber" : "123"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "accountNumber" : "123"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": [
        {
            "id": 2,
            "accountNumber": "123",
            "vpa": null,
            "blockedVpa": null,
            "blockedVpaName": null,
            "blockedMobileNumber": "7827737375",
            "updatedTs": null,
            "createdTs": null,
            "blockedUserName": "bala"
        },
        {
            "id": 104,
            "accountNumber": "123",
            "vpa": null,
            "blockedVpa": null,
            "blockedVpaName": null,
            "blockedMobileNumber": "2222222255",
            "updatedTs": null,
            "createdTs": null,
            "blockedUserName": "Nithya"
        },
        {
            "id": 105,
            "accountNumber": "123",
            "vpa": null,
            "blockedVpa": null,
            "blockedVpaName": null,
            "blockedMobileNumber": "8951205795",
            "updatedTs": null,
            "createdTs": null,
            "blockedUserName": "Nithya"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
