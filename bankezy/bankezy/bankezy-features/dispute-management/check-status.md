---
description: Get the Status of the Complaint by the complaint ID
---

# Check Status

{% swagger method="get" path="/check-status" baseUrl="/dispute-management/v1" summary="" %}
{% swagger-description %}
To get the current Status of the Complaint
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" %}
The token got from the 

[Get Token API](../market-place/api-specification/get-token-api.md)


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

{% tabs %}
{% tab title="Sample Curl Request" %}
```json


request:
{
    "channelType":"BBPS",
    "txnId":"1234poiuytrewq",
    "complaintRefNo":"NONBBPS67668096",
    "complaintType":"transaction"
}
	
response:
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "complaintStatus": "CAPTURED"
    }
}
```
{% endtab %}

{% tab title="Request Sample" %}
```json
	
{
    "channelType":"BBPS",
    "txnId":"1234poiuytrewq",
    "complaintRefNo":"NONBBPS67668096",
    "complaintType":"transaction"
}

```
{% endtab %}

{% tab title="Response Sample" %}


```
{
"resCode": 200,
"resDesc": "SUCCESS",
"data": {
    "complaintStatus": "CAPTURED"
}
```

}

```
request:
{
"channelType":"BBPS",
"txnId":"1234poiuytrewq",
"complaintRefNo":"NONBBPS67668096",
"complaintType":"transaction"
```

}

```
response:
{
"resCode": 200,
"resDesc": "SUCCESS",
"data": {
    "complaintStatus": "CAPTURED"
}
```

}
{% endtab %}
{% endtabs %}
