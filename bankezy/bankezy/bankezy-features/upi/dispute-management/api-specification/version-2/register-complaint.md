---
description: >-
  Register a user complaint with the transaction details and on Successful
  registration, Complaint ID will be generated
---

# Register Complaint

{% swagger method="post" path="/raise-complaint" baseUrl="/dispute-management/v2" summary="Register a Complaint in Dispute Management system " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channelType" required="true" %}
Payment Channel Type 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnId" required="true" %}
Transaction Reference number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="reasoncode" required="true" %}
Reason Code 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="remarks" %}
Complaint remarks
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" %}
Merchant ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" required="true" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="complaintType" required="true" %}
Nature of Complaint
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="isMerchantTxn" %}

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

| Response Body        | Data Type | Field Description                                 |
| -------------------- | --------- | ------------------------------------------------- |
| statusCode           | Int       | Success & Failure status code of the transactions |
| statusDesc           | String    | Response Description                              |
| data.complaintRefNo  | String    | Complaint Reference number                        |
| data.complaintStatus | String    | Status of the Complaint Registration              |

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location 'https://bankezy-azure.pc.enstage-sas.com/dispute-management/v1/raise-complaint' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'Content-Type: application/json' \
--data '{
    "channelType":"BBPS",
    "txnId":"1234poiuytrewq",
    "reasonCode":101,
    "remarks":"Money not credited",
    "merchantId":"105500",
    "amount": 200,
    "complaintType": "transaction"
}'
```
{% endtab %}

{% tab title="Sample Request" %}
```json
{
    "channelType":"BBPS",
    "txnId":"1234poiuytrewq",
    "reasonCode":101,
    "remarks":"Money not credited",
    "merchantId":"105500",
    "amount": 200,
    "complaintType": "transaction"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{
    "resCode": "DIS200",
    "resDesc": "SUCCESS",
    "data": {
        "complaintRefNo": "BBPS91549569",
        "complaintStatus": "CAPTURED"
    }
}
```
{% endtab %}
{% endtabs %}
