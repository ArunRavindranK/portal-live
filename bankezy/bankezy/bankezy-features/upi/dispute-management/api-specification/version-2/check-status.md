---
description: Get the Status of the Complaint by the complaint ID
---

# Check Status

{% swagger method="post" path="/check-status" baseUrl="/dispute-management/v2" summary="" %}
{% swagger-description %}
To get the current Status of the Complaint
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" %}
The token got from the 

[Get Token API](../../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="channelType" required="true" %}
Type of the Channel
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnId" %}
Transaction ID for which Complaint is confirmed
{% endswagger-parameter %}

{% swagger-parameter in="body" name="complaintRefno" required="true" %}
Complaint Reference number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="complaintType" required="true" %}
Type of Complaint
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

| Response Body        | Data Type | Description                                       |
| -------------------- | --------- | ------------------------------------------------- |
| resCode              | Int       | Success & Failure status code of the transactions |
| resDesc              | String    | Response Description                              |
| data.complaintStatus | String    | Current Status of the Complaint                   |
| data.compaintRefNo   | String    | Complaint Reference number                        |



{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location 'https://bankezy-azure.pc.enstage-sas.com/dispute-management/v1/check-status' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'Content-Type: application/json' \
--data '{
    "channelType":"BBPS",
    "txnId":"1234poiuytrewq",
    "complaintRefNo":"NONBBPS67668096",
    "complaintType":"transaction"
}
'
```
{% endtab %}

{% tab title="Sample Request" %}
```json
{
    "channelType":"BBPS",
    "txnId":"1234poiuytrewq",
    "complaintRefNo":"NONBBPS67668096",
    "complaintType":"transaction"
}

```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
"resCode": "DIS200",
"resDesc": "SUCCESS",
"data": {
    "complaintRefNo":"NONBBPS67668096",
    "complaintStatus": "CAPTURED"
}
}
```
{% endtab %}
{% endtabs %}
