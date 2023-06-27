---
description: This API used to do authentication for netbanking transaction
---

# Initiate Authentication API



{% swagger method="post" path="" baseUrl="<domain>/payments/nb/v2/txn/auth" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankCode" type="String" %}
​Bank Code
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryAccountNumber" type="String" required="true" %}
Beneficiary bank account number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardData.cvv2" %}
3 digit secured cvv number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardData.refId" %}
card reference Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="categoryId" type="String" required="true" %}
Purchase Category Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.appId" type="String" required="true" %}
wallet or SDK
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.appInstalled" type="Boolean" required="true" %}
mention app is installed in user device or notDevice relea
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.deviceId" type="String" required="true" %}
Device identification number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.deviceIdType" type="String" required="true" %}
Type of the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.deviceMake" type="String" required="true" %}
Device Make company name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.deviceMetaData1" type="JSON" required="true" %}
Device releated information
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.deviceMetaData2" required="true" %}
Device releated information
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.deviceMetaData3" type="String" required="true" %}
Device releated information
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.deviceMetaData4" type="String" required="true" %}
Device released information
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.deviceModel" type="String" required="true" %}
Device model name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.deviceProof" type="String" required="true" %}
Device releated information
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.deviceType" type="String" required="true" %}
Device releated information
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.extraData" type="String" required="true" %}
Device releated information
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.osType" type="String" required="true" %}
Type of OS installed in the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.osVersion" type="String" required="true" %}
version fof the OS installed int he device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.simID" type="String" required="true" %}
unique identification number for the sim
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.simIDProof" required="true" %}
sim  ID proof of the deivce
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo.simProof" required="true" %}
sim proof of the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wibmoAppVersion" required="true" %}
Wibmo BankEzy app version
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wibmoSdkVersion" required="true" %}
Wibmo sdk verion
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantTxnId" required="true" %}
Transaction unique id from merchant
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMode" required="true" %}
Payment mode for Netbanking is NB
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wibmoTxnId" type="String" required="true" %}
Transaction unique from wibmo
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
{% endswagger %}

## Response Details

| Response Field   | Field description         | Data Type |
| ---------------- | ------------------------- | --------- |
| actionCode       | ​action code              | String    |
| txnId            | payment transaction id    | String    |
| merchantTxnRefNo | merchant transaction id   | String    |
| txnStatus        | status of the transaction | String    |
| unmappedStatus   | status of the transaction | String    |
| htmlEncData      | data to be posted         | String    |

#### Custom Response Code

| Response Code | Response Description                                              |
| ------------- | ----------------------------------------------------------------- |
| PMT200        | SUCCESS                                                           |
| PMT001        | Execution Failure                                                 |
| PMT002        | Request could not be processed at this time.., Please retry again |
| PMT003        | Bad request                                                       |
| PMT005        | Invalid paymentTxnId                                              |

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'http://localhost:2442/payments/nb/v2/txn/auth' \
\--header 'X-ACCOUNT-NUMBER: 1896'
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=6856076DB420C282F7DAD1775520791F' \
--data-raw '{
    "bankCode": "HDFB",
    "deviceInfo": {
        "appId": "com.wibmo.wibmo_banking.stage",
        "appInstalled": "false",
        "deviceId": "anid:Z6P7WSjDm/J1JeW55VRuKFXxHkDbG9ed6zz6X16PDzs=:4e66",
        "deviceMake": "Realme",
        "deviceMetaData1": "NA",
        "deviceMetaData2": "NA",
        "deviceMetaData3": "NA",
        "deviceMetaData4": "NA",
        "deviceModel": "RMX1825",
        "deviceProof": "NA",
        "deviceType": "3",
        "extraData": "NA",
        "osType": "Android",
        "osVersion": "10",
        "simID": "NA",
        "simIDProof": "NA",
        "simProof": "NA",
        "wibmoAppVersion": "2.18.00.02.staging",
        "wibmoSdkVersion": "NA"
    },
    "merchantId": "171756421435003980",
    "merchantTxnId": "202207180414444561nH32wP1",
    "paymentMode": "NB",
    "userId": "1896", wibmoTxnId="2022071810010010161"
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "bankCode": "HDFB",
    "deviceInfo": {
        "appId": "com.wibmo.wibmo_banking.stage",
        "appInstalled": "false",
        "deviceId": "anid:Z6P7WSjDm/J1JeW55VRuKFXxHkDbG9ed6zz6X16PDzs=:4e66",
        "deviceMake": "Realme",
        "deviceMetaData1": "NA",
        "deviceMetaData2": "NA",
        "deviceMetaData3": "NA",
        "deviceMetaData4": "NA",
        "deviceModel": "RMX1825",
        "deviceProof": "NA",
        "deviceType": "3",
        "extraData": "NA",
        "osType": "Android",
        "osVersion": "10",
        "simID": "NA",
        "simIDProof": "NA",
        "simProof": "NA",
        "wibmoAppVersion": "2.18.00.02.staging",
        "wibmoSdkVersion": "NA"
    },
    "merchantId": "171756421435003980",
    "merchantTxnId": "202207180414444561nH32wP1",
    "paymentMode": "NB",
    "userId": "1896", 
    "wibmoTxnId":"2022071810010010161"
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": "200",
    "resDesc": "SUCCESS",
    "data": {
        "actionCode": "1",
        "txnId": "220718094450705",
        "merchantTxnRefNo": "2022071810010010161",
        "txnStatus": "pending",
        "unmappedStatus": "pending",
        "htmlEncData": "PGh0bWw+Cjxmb3JtIG1ldGhvZD0icG9zdCIgYWN0aW9uPSJodHRwczovL2FwaS1wejIucGMuZW5zdGFnZS1zYXMuY29tL3NpbXVsYXRlcnMvbmV0YmFua2luZy9hdXRoIj4KPGlucHV0IHR5cGU9InRleHQiIG5hbWU9InVzZXJOYW1lIiA+PGJyLz4KPGlucHV0IHR5cGU9InBhc3N3b3JkIiBuYW1lPSJwYXNzd29yZCIgPjxici8+CjxpbnB1dCB0eXBlPSJoaWRkZW4iIG5hbWU9Im1lcmNoYW50VHhuUmVmTm8iIHZhbHVlPSIyMDIyMDcxODEwMDEwMDEwMTYxIj4KPGlucHV0IHR5cGU9ImhpZGRlbiIgbmFtZT0ibWVyY2hhbnRJZCIgdmFsdWU9IjU1MTg5MDIzIj4KPGlucHV0IHR5cGU9ImhpZGRlbiIgbmFtZT0iYW1vdW50IiB2YWx1ZT0iNjAwIj4KPGlucHV0IHR5cGU9ImhpZGRlbiIgbmFtZT0icHJvZHVjdGluZm8iIHZhbHVlPSJMb2FkTW9uZXkiPgo8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJiYW5rQWNjb3VudE51bWJlciIgdmFsdWU9Im51bGwiPgo8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJwaG9uZSIgdmFsdWU9IjcwMjIwNzAyMTkiPgo8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJlbWFpbCIgdmFsdWU9Ik5pdGh5YUB3aWJtby5jb20iPgo8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJmaXJzdG5hbWUiIHZhbHVlPSJOaXRoeWEiPgo8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJzdXJsIiB2YWx1ZT0iaHR0cHM6Ly9hcGktcHoyLnBjLmVuc3RhZ2Utc2FzLmNvbS9yZWRpcmVjdC9wYXltZW50cy8xMTExL25iL3R4bi9wb3N0QXV0aFJlc3BvbnNlVG9TZXJ2ZXIiPgo8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJmdXJsIiB2YWx1ZT0iaHR0cHM6Ly9hcGktcHoyLnBjLmVuc3RhZ2Utc2FzLmNvbS9yZWRpcmVjdC9wYXltZW50cy8xMTExL25iL3R4bi9wb3N0QXV0aFJlc3BvbnNlVG9TZXJ2ZXIiPgo8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJUeG5JZCIgdmFsdWU9IjIyMDcxODA5NDQ1MDcwNSI+CjxpbnB1dCB0eXBlPSJoaWRkZW4iIG5hbWU9InVkZjEiIHZhbHVlPSIiPgo8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJ1ZGYyIiB2YWx1ZT0iIj4KPGlucHV0IHR5cGU9ImhpZGRlbiIgbmFtZT0idWRmMyIgdmFsdWU9IiI+CjxpbnB1dCB0eXBlPSJoaWRkZW4iIG5hbWU9InVkZjQiIHZhbHVlPSIiPgo8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJ1ZGY1IiB2YWx1ZT0iIj4KPGlucHV0IHR5cGU9InN1Ym1pdCIgIHZhbHVlPSJzdWJtaXQiPgo8L2Zvcm0+CjwvaHRtbD4="
    }
```
{% endtab %}
{% endtabs %}
