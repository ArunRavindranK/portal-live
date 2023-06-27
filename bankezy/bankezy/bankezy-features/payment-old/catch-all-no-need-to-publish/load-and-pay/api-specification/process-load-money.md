# Process Load Money

When user tries to complete a payment in merchant payment site using BankEzy wallet, If user's wallet has a balance less than the transaction amount then this API helps to load the required money and complete a transaction.

{% swagger method="post" path="" baseUrl="<domain>/txn/loadMoney/process/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER " type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="amountToAdd" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankCode" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardRefId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="cvv" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceInfo" type="JSON" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="appId" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="appInstalled" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceIDProof" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceIdType" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceMake" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceMetaData1" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceMetaData2" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceMetaData3" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceMetaData4" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceModel" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceProof" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceType" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="extraData" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="osType" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="osVersion" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="simID" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="simIDProof" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="simProof" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wibmoAppVersion" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wibmoSdkVersion" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMode" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wibmoTxnId" type="Boolean" %}

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
{% endswagger %}

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'http://localhost:8912/orchestrate/v1/validation' \
--header 'X-PROGRAM-ID: 1111' \
--header 'X-ACCOUNT-NUMBER: 665' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=221E003A0FEB1DFA3D25054F57008EF8' \
--data-raw '{
  "amountToAdd": "100",
    "deviceInfo":{
        "appId": "com.wibmo.wibmo_banking.qa",
        "appInstalled": "false",
        "deviceId": "tdid:GZLmEcsmuf0mZpxu+Vk9NWrPhLigYdzBQTm+rkn4WVo=:2376",
        "deviceMake": "OPPO",
        "deviceMetaData1": "NA",
        "deviceMetaData2": "NA",
        "deviceMetaData3": "NA",
        "deviceMetaData4": "NA",
        "deviceModel": "CPH1893",
        "deviceProof": "NA",
        "deviceType": "3",
        "extraData": "NA",
        "osType": "Android",
        "osVersion": "9",
        "simID": "NA",
        "simIDProof": "NA",
        "simProof": "NA",
        "wibmoAppVersion": "2.15.00.04.qa",
        "wibmoSdkVersion": "NA"
    }, 
  "paymentMode": "WC",
  "wibmoTxnId": "202208011105327855bP02aI5"
}'
```
{% endtab %}

{% tab title="Request" %}


```
{
  "amountToAdd": "100",
  "deviceInfo": {
    "appId": "string",
    "appInstalled": true,
    "deviceIDProof": "string",
    "deviceId": "string",
    "deviceIdType": 0,
    "deviceMake": "string",
    "deviceMetaData1": "string",
    "deviceMetaData2": "string",
    "deviceMetaData3": "string",
    "deviceMetaData4": "string",
    "deviceModel": "string",
    "deviceProof": "string",
    "deviceType": 0,
    "extraData": "string",
    "osType": "string",
    "osVersion": "string",
    "simID": "string",
    "simIDProof": "string",
    "simProof": "string",
    "wibmoAppVersion": "string",
    "wibmoSdkVersion": "string"
  },
  "paymentMode": "WC",
  "wibmoTxnId": "202208011105327855bP02aI5"
}
```
{% endtab %}

{% tab title="Response" %}
```json
// Some code
```
{% endtab %}
{% endtabs %}
