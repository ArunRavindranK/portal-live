---
description: To Perform Recharge for the transaction
---

# Recharge Request API

{% swagger method="post" path="recharge/v1/request" baseUrl="<domain>/retail-service/" summary="To Perform Recharge for the transaction" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
will be shared upon onboarding api consumers (clients)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="resCode" type="String" required="true" %}
Payment Authentication Success Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="resDesc" type="String" required="true" %}
Payment Authentication Success Description
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionReferenceNumber" type="String" required="true" %}
Unique transaction reference Number generated for the transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wibmoTxnId" type="String" required="true" %}
wibmo payment txn Id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="CONTENT-TYPE" required="true" %}
text/plain
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
{% endswagger %}

## Response Details

| Response Body                        | Data Type | Field Description                                        |
| ------------------------------------ | --------- | -------------------------------------------------------- |
| statusCode                           | int       | Success & Failure codes of the transaction               |
| statusDesc                           | String    | Response Description                                     |
| transactionReferenceNumber           | String    | Unique transaction reference ID.                         |
| subscriberId                         | String    | The mobile number recharged                              |
| rechargeAmount                       | String    | Transactional amount                                     |
| operatorName                         | String    | Name of the operator                                     |
| spReferenceNumber                    | String    | Reference number from the service provider               |
| billerId                             | String    | Unique biller ID for the bill payment transaction        |
| timeToPollRechargeStatusAPIInSeconds | String    | Time to check the status if the request is of Async type |
| transactionDate                      | String    | Transaction time stamp                                   |

{% tabs %}
{% tab title="sample curl  Request " %}
```json
curl --location --request POST 'https://app9.pcdev.enstage-sas.com/retail-service/recharge/v1/request' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'Content-Type: text/plain' \
--data-raw '{
  "resCode": "00",
  "resDesc": "success",
  "transactionReferenceNumber": "11112022072108111549922028435879142",
  "wibmoTxnId": "2022062010010010300"
}'
```


{% endtab %}

{% tab title="Request Example" %}
```json
{
  "resCode": "00",
  "resDesc": "success",
  "transactionReferenceNumber": "11112022072108111549922028435879142",
  "wibmoTxnId": "2022062010010010300"
}
```




{% endtab %}

{% tab title="Response Example" %}
```json
{
    "responseTimeTakenMs": 0,
    "statusCode": 200,
    "statusDesc": "SUCCESS",
    "data": {
        "transactionReferenceNumber": "11112022072108111549922028435879142",
        "subscriberId": "9620686057",
        "rechargeAmount": "79.00",
        "operatorName": "IC",
        "spReferenceNumber": "PU02207",
        "billerId": "IDEAPREPAID",
        "timeToPollRechargeStatusAPIInSeconds": 3,
        "transactionDate": "2022-07-22 15:11:24"
    }
}
```


{% endtab %}
{% endtabs %}
