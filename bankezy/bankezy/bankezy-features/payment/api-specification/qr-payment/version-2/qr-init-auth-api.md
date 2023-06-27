---
description: This API helps to initiate a transaction in bankEzy using favorite card.
---

# QR Init Auth API

{% swagger method="post" path="" baseUrl="<domain>/qrTxn/init/api/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="long" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="int" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" required="true" %}
Id number for a merchant. This will be generated at the time of merchant onboarding process
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantName" required="true" %}
name of a merchant. This will be generated at the time of merchant onboarding process
{% endswagger-parameter %}

{% swagger-parameter in="body" name="qrCode" required="true" %}
qr code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCategoryCode" type="String" required="true" %}
merchant Category Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCityName" required="true" %}
merchant City Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCountryCode" required="true" %}
merchant Country Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="primaryId" type="String" required="false" %}
primary Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="secondaryId" %}
secondary Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionDesc" required="true" %}
transaction Description
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionCurrencyCode" required="true" %}
transaction Currency Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tipAndFeeIndicator" type="String" %}
tip and fee indicator
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerId" type="long" required="true" %}
customer id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tipCalculatedAmount" type="long" required="true" %}
tip calculated amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionAmount" type="long" required="true" %}
transaction amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RecurringPaymentDetails.expiryDate" %}
If recurring payment enable. this field is mandatory. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="convenienceFeeAmount" type="int" required="true" %}
convenience fee amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="convenienceFeePercentage" type="int" required="true" %}
convenience fee percentage
{% endswagger-parameter %}

{% swagger-parameter in="body" name="qrVersion" type="String" required="true" %}
qr version
{% endswagger-parameter %}

{% swagger-parameter in="body" name="qrType" type="String" required="true" %}
qr type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantPostalCode" required="true" %}
merchant postal code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="primaryIdTag" %}
primary id tag
{% endswagger-parameter %}

{% swagger-parameter in="body" name="secondaryIdTag" %}
secondary id tag
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ifscAndAccountNumber" required="true" %}
IFSC and accountnumber
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" required="true" %}
mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" required="true" type="int" %}
country code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cvv2" %}
cvv2
{% endswagger-parameter %}

{% swagger-parameter in="body" name="refId" required="true" %}
reference id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMode" required="true" %}
payment mode
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
curl --location --request POST 'http://localhost:2442/qrTxn/init/api/v1' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=1EFD299E213DEE8847A52413CD0FB47E' \
--data-raw '{
    "convenienceFeeAmount": 0,
    "convenienceFeePercentage": 0,
    "countryCode": 91,
    "customerId": "665",
    "deviceInfo": {
        "appId": "com.wibmo.wibmo_banking.dev",
        "appInstalled": false,
        "deviceId": "anid:AloZHNC6ehWfiK4lgVoNIsq3wRGpIe5y8sGJn/ey8Ws=:1ffe",
        "deviceMake": "samsung",
        "deviceMetaData1": "NA",
        "deviceMetaData2": "NA",
        "deviceMetaData3": "NA",
        "deviceMetaData4": "NA",
        "deviceModel": "SM-G996B",
        "deviceProof": "NA",
        "deviceType": "3",
        "extraData": "NA",
        "osType": "Android",
        "osVersion": "12",
        "simID": "NA",
        "simIDProof": "NA",
        "simProof": "NA",
        "wibmoAppVersion": "2.11.00.00.dev.dev",
        "wibmoSdkVersion": "NA"
    },
    "ifscAndAccountNumber": "BKID0000046004611100035771",
    "merchantCategoryCode": "7299",
    "merchantCityName": "MUMBAI",
    "merchantCountryCode": "IN",
    "merchantId": "4311191000000003",
    "merchantName": "BHARAT STORES",
    "merchantPostalCode": "400051",
    "mobile": "8892231111",
    "paymentMode":"WC",
    "qrAddDataField": {
        "tag07": "00000003"
    },
    "qrCode": "000201010211021643111910000000030415542034000000001061661000600000000340826BKID00000460046111000357715204729953033565802IN5913BHARAT STORES6006MUMBAI610640005162120708000000036304C377",
    "qrType": "MVISA",
    "qrVersion": "01",
    "refId":"114",
    "tipCalculatedAmount": 0,
    "transactionAmount": 100,
    "transactionCurrencyCode": "356",
    "transactionDesc": "NA"
}'
```
{% endtab %}

{% tab title="Request Sample" %}
```json
{
    "convenienceFeeAmount": 0,
    "convenienceFeePercentage": 0,
    "countryCode": 91,
    "customerId": "665",
    "deviceInfo": {
        "appId": "com.wibmo.wibmo_banking.dev",
        "appInstalled": false,
        "deviceId": "anid:AloZHNC6ehWfiK4lgVoNIsq3wRGpIe5y8sGJn/ey8Ws=:1ffe",
        "deviceMake": "samsung",
        "deviceMetaData1": "NA",
        "deviceMetaData2": "NA",
        "deviceMetaData3": "NA",
        "deviceMetaData4": "NA",
        "deviceModel": "SM-G996B",
        "deviceProof": "NA",
        "deviceType": "3",
        "extraData": "NA",
        "osType": "Android",
        "osVersion": "12",
        "simID": "NA",
        "simIDProof": "NA",
        "simProof": "NA",
        "wibmoAppVersion": "2.11.00.00.dev.dev",
        "wibmoSdkVersion": "NA"
    },
    "ifscAndAccountNumber": "BKID0000046004611100035771",
    "merchantCategoryCode": "7299",
    "merchantCityName": "MUMBAI",
    "merchantCountryCode": "IN",
    "merchantId": "4311191000000003",
    "merchantName": "BHARAT STORES",
    "merchantPostalCode": "400051",
    "mobile": "8892231111",
    "paymentMode":"WC",
    "qrAddDataField": {
        "tag07": "00000003"
    },
    "qrCode": "000201010211021643111910000000030415542034000000001061661000600000000340826BKID00000460046111000357715204729953033565802IN5913BHARAT STORES6006MUMBAI610640005162120708000000036304C377",
    "qrType": "MVISA",
    "qrVersion": "01",
    "refId":"114",
    "tipCalculatedAmount": 0,
    "transactionAmount": 100,
    "transactionCurrencyCode": "356",
    "transactionDesc": "NA"
}
```
{% endtab %}

{% tab title="Response Sample" %}
```json
{
    "resCode": "200",
    "resDesc": "SUCCESS",
    "data": {        
        "merchantId": "4311191000000003",
        "merchantName": "Bharat Stores",
        "merchantTxnId": "QR20230529089qe8uW",
        "merchantReturnUrl": null,
        "txnAmt": 100,
        "txnDesc": "QR Payment",
        "txnFormattedAmount": "Rs. 1.00",
        "wibmoTxnId": "2023052910010010285",
        "recurringPaymentRefId": 0,
        "supportedPaymentType": [
            "UPII"
        ],
        "restrictedPaymentType": [
            "w.ds.pt.none"
        ],
        "cardFee": null
    }
}
```
{% endtab %}
{% endtabs %}
