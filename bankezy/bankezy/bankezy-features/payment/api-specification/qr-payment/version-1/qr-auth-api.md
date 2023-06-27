---
description: This API helps to initiate a transaction in bankEzy
---

# QR Auth API

{% swagger method="post" path="" baseUrl="<domain>/qrTxn/process/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="long" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="int" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCountryCode" type="String" required="true" %}
merchant country code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" required="true" %}
merchant id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantName" required="true" %}
merchant name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wibmoTxnId" type="long" required="true" %}
wibmo txn id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantTxnId" required="true" %}
merchant txn id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="qrType" required="true" type="String" %}
qr type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="programId" type="String" required="true" %}
program id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInfo.userConsent" type="boolean" required="true" %}
user consent
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInfo.cardNumber" required="true" %}
cardNumber
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInfo.cardType" required="true" %}
cardType
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInfo.cardToken" type="String" required="true" %}
cardToken
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInfo.walletId" type="int" required="true" %}
walletId
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

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request POST 'http://localhost:2442/qrTxn/process/api/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=1EFD299E213DEE8847A52413CD0FB47E' \
--data-raw '{
    "merchantCountryCode": "IN",
    "merchantId": "4311191000000003",
    "merchantName": "Bharat Stores",
    "resCode": null,
    "resDesc": null,
    "wibmoTxnId": 2023052610010010034,
    "merchantTxnId": "QR2023052609Zr934H",
    "customerId": 2605,
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
    },
    "qrType": "MASTER_QR",
    "programId": "1111",
    "paymentInfo": {
        "userConsent": false,
        "cardNumber": "5123456789012346",
        "cardType": "MAST",
        "cardToken": null,
        "walletId": 0
    }
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "merchantCountryCode": "IN",
    "merchantId": "4311191000000003",
    "merchantName": "Bharat Stores",
    "wibmoTxnId": 2023052610010010034,
    "merchantTxnId": "QR2023052609Zr934H",
    "customerId": 2605,
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
    },
    "qrType": "MASTER_QR",
    "programId": "1111",
    "paymentInfo": {
        "userConsent": false,
        "cardNumber": "5123456789012346",
        "cardType": "MAST",
        "cardToken": null,
        "walletId": 0
    }
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": "200",
    "resDesc": "SUCCESS",
    "data": {      
        "wibmoTxnId": "2023052910010010285",  
        "merTxnId": "QR20230529089qe8uW",
        "chargeSuccess":true,
        "pgTxnId": "4311191000000003",
        "cardType": "Bharat Stores",
        "txnAmt": 100,
        "cardClassificationType": "QR Payment",
        "cardMasked": "Rs. 1.00",
        "pgStatusCode": "",
        "paymentType":"Card"
        "paymentDetails": {
        }
    }
}
```
{% endtab %}
{% endtabs %}
