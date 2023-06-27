---
description: This API helps to initiate a transaction in bankEzy
---

# Consent API

{% swagger method="post" path="" baseUrl="<domain>/payments/consent/txn/init/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="long" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="int" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="long" required="true" %}
Id number for a merchant. This will be generated at the time of merchant onboarding process
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmt" type="long" required="true" %}
user entered transaction amount without implied decimal format
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDesc" required="true" %}
Any description for the transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" required="true" %}
Transaction type Example : IAP (InApp Payment)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="acccountNumber" type="long" required="true" %}
user unique account number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo" %}
If recurring payment enable. this field is mandatory. 
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

## Custom Response codes

| Response code | Response description       |
| ------------- | -------------------------- |
| 106           | Merchant doesn't exist !!! |
| 100           | Execution Failure.         |

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request POST 'http://localhost:2442/payments/consent/txn/init/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=1EFD299E213DEE8847A52413CD0FB47E' \
--data-raw '{
    "txnAmt": 100,
    "merchantId": 4311191000000003,
    "txnDesc": "Bharat Stores",
    "txnType": "TC",
    "acccountNumber": 123,
    "deviceInfo": {
        "wibmoSdkVersion": "NA",
        "wibmoAppVersion": "2.17.00.00.dev.debug",
        "deviceId": "869444038443107",
        "deviceMake": "Xiaomi",
        "deviceModel": "Redmi Note 5 Pro",
        "osType": "Android",
        "osVersion": 9,
        "appInstalled": false,
        "deviceIdType": 0,
        "deviceType": 3,
        "deviceIDProof": null,
        "simID": "NA",
        "simIDProof": "NA",
        "appId": "com.wibmo.wibmo_banking.bankezy.dev",
        "deviceProof": "NA",
        "simProof": "NA",
        "deviceMetaData1": "NA",
        "extraData": "NA",
        "deviceMetaData2": "NA",
        "deviceMetaData3": "NA",
        "deviceMetaData4": "NA"
    }
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "txnAmt": 100,
    "merchantId": 4311191000000003,
    "txnDesc": "Bharat Stores",
    "txnType": "TC",
    "acccountNumber": 123,
    "deviceInfo": {
        "wibmoSdkVersion": "NA",
        "wibmoAppVersion": "2.17.00.00.dev.debug",
        "deviceId": "869444038443107",
        "deviceMake": "Xiaomi",
        "deviceModel": "Redmi Note 5 Pro",
        "osType": "Android",
        "osVersion": 9,
        "appInstalled": false,
        "deviceIdType": 0,
        "deviceType": 3,
        "deviceIDProof": null,
        "simID": "NA",
        "simIDProof": "NA",
        "appId": "com.wibmo.wibmo_banking.bankezy.dev",
        "deviceProof": "NA",
        "simProof": "NA",
        "deviceMetaData1": "NA",
        "extraData": "NA",
        "deviceMetaData2": "NA",
        "deviceMetaData3": "NA",
        "deviceMetaData4": "NA"
    }
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "merchantId": 171756421435003980,
        "merchantTxnId": "202204251412233239dW90yA8",
        "txnAmt": 10000,
        "txnDesc": "Consent",
        "txnFormattedAmount": "Rs. 100.00",
        "wibmoTxnId": 2022072210010010007
    }
}
```
{% endtab %}
{% endtabs %}
