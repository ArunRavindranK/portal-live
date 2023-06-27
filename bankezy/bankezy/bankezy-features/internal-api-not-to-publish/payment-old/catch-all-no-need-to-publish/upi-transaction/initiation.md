---
description: This API helps to initiate a UPI  transaction
---

# Initiation

{% swagger method="get" path="" baseUrl="<domain>/payments/upi/txn/init/auth/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="x-account-number" required="true" type="long" %}
Account Number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-program-id" required="true" type="int" %}
Tenant Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pspRefNo" type="long" required="true" %}
PSP reference number is mandatory
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantTxnId" required="true" %}
Merchant transaction Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVirtualAddress" required="true" %}
VPA of payer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerAccountId" required="true" %}
Account id of payer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNo" required="true" %}
Mobile number of payer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="geoCode" required="true" %}
Geo code of payer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" required="true" %}
Location of payer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ip" required="true" %}
Ip address of payer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="appName" required="true" %}
AppName Ex. BankEzy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="capability" required="true" %}
OS name of payer device
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVirtualAddress" required="true" %}
VPA of payee
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeVPAType" required="true" %}
Payee VPA type Ex. VA - Virtual Payment address, AA - Aadhar , AC- Account
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" required="true" %}
type of transaction Ex. P2M
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMode" required="true" %}
Payment Mode Ex. UPI
{% endswagger-parameter %}

{% swagger-parameter in="body" name="initiationMode" required="true" %}
Transaction initiation mode

00 - Default

01 - SEBI

02 - AMC

03 - Travel

04 - Hospitaliaty

05 - Hospital

06 - Telecom, 07- Insurance 08 - Education 09 - Gifting 10 - Others
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pgMerchantId" required="true" %}
Merchant id from Payment gateway
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pgTID" required="true" %}
Transaction Id from Payment Gatewya
{% endswagger-parameter %}

{% swagger-parameter in="body" name="upiPgMerchantId" required="true" %}
Merchant id for Payment gateway for UPI
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
curl --location --request POST 'http://localhost:2442/payments/upi/txn/init/auth/v1' \
--header 'x-account-number: 3513' \
--header 'x-program-id: 1111' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=39ABD7D35400DEBCE867CB38AD2F9DFD' \
--data-raw '{
    "appName": "Bankezy",
    "capability": "Android",
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
    "geoCode": "India",
    "location": "India",
    "merchantTxnId": "11112022071804420533010192132039075",
    "mobileNo": "9019632972",
    "payeeVirtualAddress": "81516121@bankezy",
    "payerAccountId": "9165028",
    "payerVirtualAddress": "9019632972@bankezy",
    "pspRefNo": "2022071810010010344"
}'
```
{% endtab %}

{% tab title="Request" %}
```json
{
    "appName": "Bankezy",
    "capability": "Android",
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
    "geoCode": "India",
    "location": "India",
    "merchantTxnId": "11112022071804420533010192132039075",
    "mobileNo": "9019632972",
    "payeeVirtualAddress": "81516121@bankezy",
    "payerAccountId": "9165028",
    "payerVirtualAddress": "9019632972@bankezy",
    "pspRefNo": "2022071810010010344"
}
```
{% endtab %}

{% tab title="Response" %}
```json5
{
    "resCode": "200",
    "resDesc": "SUCCESS",
    "data": {
        "pspRefNo": "2022071810010010344",
        "upiTxnRefNo": "9d36e3",
        "npciTxnId": "9862ba3c-411c-4377-9fca-eff9ae5cde33",
        "customerRefNo": "d9968e5b-d",
        "txnAmount": "500",
        "txnReqDate": "2022:07:18 04:42:09 AM",
        "payerBankName": "My Bank",
        "mobileNo": "9019632972",
        "deviceId": "anid:Z6P7WSjDm/J1JeW55VRuKFXxHkDbG9ed6zz6X16PDzs=:4e66",
        "appName": "Bankezy",
        "payerAddress": "9019632972@bankezy",
        "payeeAddress": "81516121@bankezy",
        "payerName": "Test Merchant",
        "txnNote": "Recharge",
        "refId": "",
        "refURL": "https://upitest.hdfcbank.com",
        "accountNo": "XXXXXX1264",
        "credentialDateType": "NUM",
        "credentialDataLength": "6",
        "status": "S",
        "statusDescription": "00",
        "chargeAttempted": "true",
        "merTxnId": "11112022071804420533010192132039075",
        "merchantId": "81516121",
        "commonInfo": {
            "additionalField1": "",
            "additionalField2": "",
            "additionalField3": "",
            "additionalField4": "",
            "additionalField5": "",
            "additionalField6": "",
            "additionalField7": "",
            "additionalField8": "",
            "additionalField9": "NA",
            "additionalField10": "NA"
        }
    }
}
```
{% endtab %}
{% endtabs %}
