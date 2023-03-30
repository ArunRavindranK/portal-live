---
description: >-
  This API helps to initiate a card based authentication request once initiation
  successful
---

# Authentication API

{% swagger method="get" path="" baseUrl="<domain>/payments/txn/auth/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="int" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" type="long" name="wibmoTxnId" required="true" %}
Wibmo transaction id. From init response user can get wibmoTxnId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantTxnId" required="true" %}
Merchant transaction Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMode" required="true" %}
Payment mode can be LC/NB/WC
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankCode" %}
Bankcode is required is payment mode netbanking (NB)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiaryAccountNumber" %}
Beneficiary account number is mandatory for TPV payments
{% endswagger-parameter %}

{% swagger-parameter in="body" name="categoryId" type="int" %}
Merchant category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.wibmoSdkVersion" required="true" %}
Wibmo app installed version
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.wibmoAppVersion" required="true" %}
Wibmo sdk installed version
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceId" required="true" %}
User device unique id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceMake" required="true" %}
User device make name Ex, Samsung
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceModel" required="true" %}
User device model name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.osType" required="true" %}
User device installed OS name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.osVersion" required="true" %}
User device installed OS version
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.appInstalled" type="boolean" required="true" %}
Wibmo app installed status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceIdType" type="int" required="true" %}
Type of the device id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceType" type="int" required="true" %}
Type of the device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceIDProof" required="true" %}
Device id proof
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.simID" required="true" %}
User device Sim id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.simIDProof" required="true" %}
User device sim id proof
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.appId" required="true" %}
Application id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceProof" required="true" %}
Device proof
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.simProof" required="true" %}
Sim proof
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceMetaData1" required="true" %}
Additional device data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.extraData" required="true" %}
Extra data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceMetaData2" required="true" %}
Additional device data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceMetaData3" required="true" %}
Additional device data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DeviceInfo.deviceMetaData4" required="true" %}
Additional device data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="CardData.cvv2" required="true" %}
Card secured cvv number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="CardData.refIfd" required="true" %}
Linked card reference id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
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
```json5
curl --location --request POST 'http://localhost:2442/payments/txn/auth/v1' \
\--header 'x-account-number: 665'
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=39ABD7D35400DEBCE867CB38AD2F9DFD' \
--data-raw '{
    "cardData":{
        "cvv2": "XXX",
        "refId": "795"
    }, 
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
    "merchantId":"171756421435003980", 
    "merchantName":"Load Money. Merchant", 
    "merchantTxnId":"202204251412233239dW90yA8", 
    "paymentMode":"LC", 
    "txnAmt":"10000", 
    "txnDesc":"LoadMoney", 
    "userId":"665", 
    "wibmoTxnId":"2022072210010010031"
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "cardData":{
        "cvv2": "XXX",
        "refId": "795"
    }, 
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
    "merchantId":"171756421435003980", 
    "merchantName":"Load Money. Merchant", 
    "merchantTxnId":"202204251412233239dW90yA8", 
    "paymentMode":"LC", 
    "txnAmt":"10000", 
    "txnDesc":"LoadMoney", 
    "userId":"665", 
    "wibmoTxnId":"2022072210010010031"
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "actionCode": 1,
        "additionalUserInputData": {
            "browserKeyValue": [
                {
                    "id": "mpiErrorCode",
                    "value": "000"
                },
                {
                    "id": "return-url",
                    "value": "https://payment1.pcdev.enstage-sas.com/redirect/payments/txn/postAuthResponseToServer"
                },
                {
                    "id": "mpiErrorDesc",
                    "value": ""
                },
                {
                    "id": "s2s_id",
                    "value": "MjAyMjA3MjI0OTk1MDg"
                },
                {
                    "id": "md",
                    "value": "2022072210010010031"
                },
                {
                    "id": "merchant_id",
                    "value": "Wibmo_OpsUAT1"
                }
            ],
            "formInput": [
                {
                    "id": "METHOD_IDENTIFIER",
                    "label": null,
                    "minLength": 0,
                    "maxLength": 0,
                    "inputType": "HID",
                    "comment": null,
                    "allowStore": false,
                    "encryption": false,
                    "editable": false,
                    "inputValue": "RESPONSE_FROM_EXTERANL_SOURCE",
                    "mandatory": false
                }
            ],
            "mdStr": null,
            "inflowTxnId": null,
            "redirectFormAction": "https://wibmompiuat-dw.pc.enstage-sas.com/MultiMPI/MPIServer?perform=s2sProcessing",
            "redirectFormMethod": "post",
            "redirectPageText": "3DSecure Transaction is being processed, Please wait ...",
            "returnUrl": "https://payment1.pcdev.enstage-sas.com/redirect/payments/txn/postAuthResponseToServer"
        },
        "wibmoTxnId": 2022072210010010031,
        "merTxnId": "202204251412233239dW90yA8",
        "responseCode": "000",
        "responseDescription": "SUCCESS",
        "merchantId": 171756421435003980,
        "txnAmt": 10000,
        "chargeAttempted": false,
        "txnDate": 1658495155000,
        "supportedPaymentType": null,
        "restrictedPaymentType": null
    }
}
```
{% endtab %}
{% endtabs %}
