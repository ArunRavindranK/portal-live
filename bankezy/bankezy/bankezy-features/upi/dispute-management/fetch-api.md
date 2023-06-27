---
description: Get the Status of the Complaint by the complaint ID
---

# Fetch API

{% swagger method="post" path="/fetch" baseUrl="/dispute-management/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
token to access api
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" required="false" %}
Type of the Channel
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
Program Id 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fromDate" required="true" %}
from Date to fetch list of records
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" %}
Account number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="toDate" required="false" %}
to Date to fetch list of records
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" required="false" %}
status 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="offset" required="true" %}
offset to fetch the pagination records
{% endswagger-parameter %}

{% swagger-parameter in="body" name="limit" required="true" %}
limit to fetch records
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channelType" required="true" %}
Type of the Channel
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
{% endswagger %}



| Response Body | Data Type | Description                                       |
| ------------- | --------- | ------------------------------------------------- |
| resCode       | Int       | Success & Failure status code of the transactions |
| resDesc       | String    | Response Description                              |
| data          | Object    | List of response objects                          |



| Response Body   | Data Type | Description                                  |
| --------------- | --------- | -------------------------------------------- |
| Object          |           |                                              |
| complaintRefNo  | String    | Complaint reference number raised in gateway |
| complaintStatus | String    | status of the complaint in gateway           |
| amount          | String    | amount for the transaction                   |
| status          | String    | status of the transaction                    |
| name            | String    | name                                         |
| createdTime     | String    | created time of the complaint                |
| txnId           | String    | transaction Id                               |
| transDesc       | String    | description of the transaction               |
| adjFlag         | String    |                                              |
| adjCode         | String    |                                              |



{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location 'https://bankezy-azure.pc.enstage-sas.com/dispute-management/v1/fetch' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'X-PROGRAM-ID: 2001' \
--header 'Content-Type: application/json' \
--data '{
    "type":"",
    "fromDate":"05/04/2023",
    "toDate":"",
    "status":"transaction",
    "offset":"0",
    "limit":"10",
    "channelType":"BBPS"
}
'
```
{% endtab %}

{% tab title="Sample Request" %}
```json
{
    "type":"",
    "fromDate":"05/04/2023",
    "toDate":"",
    "status":"transaction",
    "offset":"0",
    "limit":"10",
    "channelType":"BBPS"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
"resCode": 200,
"resDesc": "SUCCESS",
"data": {
    "complaintRefNo":"NONBBPS67668096",
    "complaintStatus":"PENDING"
    "amount":"100.00",
    "status":"PENDING",
    "name":"transaction",
    "createdTime":"05/04/2023",
    "txnId":"202305043456788909",
    "transDesc":"TEST Transaction",
    "adjFlag":"",
    "adjCode":""
 }
}
```
{% endtab %}
{% endtabs %}
