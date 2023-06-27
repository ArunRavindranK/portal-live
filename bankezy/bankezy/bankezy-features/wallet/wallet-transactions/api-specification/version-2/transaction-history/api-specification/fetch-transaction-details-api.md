---
description: To fetch the transaction details
---

# Fetch Transaction Details API



{% swagger method="post" path="" baseUrl="<domain>/txnHistory/v2/detail" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="action" type="String" required="true" %}
Action(Ex: MER_TXN,P2P,RM)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="category" type="String" required="true" %}
Category(Ex: LM,P2PC,P2PD)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refId" type="String" required="true" %}
Reference ID(Transaction Ref#)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
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

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Custom response codes

<table><thead><tr><th width="276.5">Code</th><th>Description</th></tr></thead><tbody><tr><td>TXH004</td><td>RefId should be greater than Zero</td></tr><tr><td>​TXH005</td><td>category id is mandatory</td></tr><tr><td>TXH002</td><td>​Please try after sometime.</td></tr><tr><td>TXH002</td><td>try after some time</td></tr><tr><td>​TXH006</td><td>​No data found</td></tr></tbody></table>

{% tabs %}
{% tab title="Sample curl command" %}
```json
​curl --location --request POST '
https://payment1.pcdev.enstage-sas.com/txnHistory/v2/detail'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:token'
--data-raw'{ "action":"MER_TXN", "category":"IAP", "refId":"489610" }'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "action": "MER_TXN",
  "category": "IAP",
  "refId": "489610"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "statusCode": "TXH200",
  "statusDesc": "Success",
  "data": {
    "transactionRefId": "11112022061310033936619177622436076",
    "spReferenceId": "PU02206",
    "amount": "7900.0",
    "status": "SUCCESS",
    "transactionDate": "2022-06-13 10:03:40",
    "subscriberName": "New Number",
    "operatorPrefix": "AT",
    "operatorName": "AIRTEL",
    "serviceId": "1",
    "rechargeType": "TOPUP"
  }
}
```
{% endtab %}
{% endtabs %}



