---
description: This API is used to get the list of blocked mobile number
---

# Blocked Mobile Number List API

{% swagger method="post" path="" baseUrl="<domain>/wallet/accountManagement/v2/blockedlist" summary="" %}
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

| Response Code | Response Desc |
| ------------- | ------------- |
| WAL200        | SUCCESS       |
| WAL100        | FAILURE       |
|               |               |

### Response Details

<table><thead><tr><th>Response Field</th><th width="143">Field Desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>response Code of the API</td><td>String</td><td></td></tr><tr><td>resDesc</td><td>response Description of the API</td><td>String</td><td></td></tr><tr><td>id</td><td>ID</td><td>long</td><td></td></tr><tr><td>accountNumber</td><td>Account Number of blocked User</td><td>String</td><td></td></tr><tr><td>vpa</td><td></td><td></td><td></td></tr><tr><td>blockedVpa</td><td>vpa of blocked User</td><td>String</td><td></td></tr><tr><td>blockedVpaName</td><td>name of blocked User</td><td>String</td><td></td></tr><tr><td>blockedMobileNumber</td><td>Mobile Number of blocked User</td><td>String</td><td></td></tr><tr><td>updatedTs</td><td>TimeStamp of entry updated</td><td>Timestamp</td><td></td></tr><tr><td>createdTs</td><td>TimeStamp of entry created</td><td>Timestamp</td><td></td></tr><tr><td>blockedUsername</td><td>name of blocked User</td><td>String</td><td></td></tr></tbody></table>

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
    "resCode": "WAL200",
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
