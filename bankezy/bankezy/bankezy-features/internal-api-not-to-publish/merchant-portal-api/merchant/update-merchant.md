---
description: This API enables the user to edit and update the Merchant details
---

# Update Merchant

{% swagger method="post" path="/mrch-management/v1/merchantDetail" baseUrl="<domain>" summary="Update merchant" %}
{% swagger-description %}
To update the merchant details for the given merchant id.
{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="merchantId" type="String" %}
Merchant id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantName" type="String" %}
Merchant name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="registeredMerchantName" type="String" %}
Registered Merchant name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="businessOwnerName" type="String" %}
Business owner name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="altMerchantName" type="String" %}
Alternate Merchant name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="businessType" type="String" %}
Business Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userType" type="String" %}
User type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="aggregatorId" type="String" %}
Aggregator id 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="partnerName1" type="String" %}
Partner name 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="partnerName2" type="String" %}
Partner name 2
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCategory" type="String" %}
Merchant category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantSubCategory" type="String" %}
Merchant sub category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mcc" type="int" %}
mcc
{% endswagger-parameter %}

{% swagger-parameter in="body" name="shopCode" type="String" %}
Shop Code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantIdRef1" type="String" %}
Merchant id Reference 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantIdRef2" type="String" %}
Merchant id Reference 2
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="String" %}
mobile
{% endswagger-parameter %}

{% swagger-parameter in="body" name="altMobile" type="String" %}
Alternate mobile
{% endswagger-parameter %}

{% swagger-parameter in="body" name="emailId" type="String" %}
Email id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="altEmailId" type="String" %}
Alternate Email id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="kycLevel" type="String" %}
Kyc level
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantStatus" type="String" %}
Merchant status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addr.addressLine1" type="String" %}
Address line 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addr.addressLine2" type="String" %}
Address line 2
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addr.addressLine3" type="String" %}
Address line 3
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addr.city" type="String" %}
City
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addr.alternateCity" type="String" %}
Alternate City
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addr.state" type="String" %}
State
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addr.country" type="String" %}
Country
{% endswagger-parameter %}

{% swagger-parameter in="body" name="addr.pinCode" type="String" %}
Pincode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankInfo.bankAccountNum" type="String" %}
Bank Account number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankInfo.ifscCode" type="String" %}
Ifsc code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankInfo.supportedCurrency" type="String" %}
Supported Currency
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankInfo.supportedDoc" type="String" %}
Supported doc
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankInfo.docValidationStatus" type="String" %}
Doc Validation status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankInfo.merchantVpa" type="String" %}
Merchant Vpa
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankInfo.walletId" type="String" %}
Wallet Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankInfo.accountStatus" type="String" %}
Account status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantKycInfo.kycDocType" type="List<String>" %}
Kyc Doc Type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantKycInfo.kycIdNum" type="List<String>" %}
Kyc Id number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantKycInfo.kycImage" type="List<String>" %}
Kyc image
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantKycInfo.kycStatus" type="List<String>" %}
Kyc status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantKycInfo.shareCode" type="List<String>" %}
Share code
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantKycInfo.gstinNumber" type="String" %}
gst in number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantKycInfo.gstinValidationStatus" type="String" %}
gst validation status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantLimit.dailyLimit" type="String" %}
Merchant Daily limit
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantLimit.monthlyLimit" type="String" %}
Merchant Monthly limit
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantLimit.yearlyLimit" type="String" %}
Merchant Yearly limit
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantLimit.dailyCount" type="String" %}
Merchant daily count
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantLimit.monthlyCount" type="String" %}
Merchant monthly count
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantLimit.yearlyCount" type="String" %}
Merchant yearly count
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantLimit.charges" type="String" %}
Merchant charges
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantLimit.rebates" type="String" %}
Merchan t rebates
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInstrument.staticQr" type="String" %}
Payment static Qr
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInstrument.dynamicQr" type="String" %}
Payment dynamic count
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInstrument.paymentLinks" type="String" %}
Payment links
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInstrument.collectPayments" type="String" %}
Collect Payments
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInstrument.payouts" type="String" %}
Payouts
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInstrument.tapNPay" type="String" %}
Tap N pay
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentInstrument.urlQr" type="String" %}
Url Qr
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantParameters.bulkQR" type="String" %}
Bulk Qr
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantParameters.financeReq" type="String" %}
Finance Request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantParameters.merchantLink" type="String" %}
Merchant Link
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantParameters.merchantUrl" type="String" %}
Merchant Url
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantParameters.monthlySales" type="String" %}
Monthly Sales
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantParameters.langPreference" type="String" %}
Language Preference
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMethods.netBanking" type="String" %}
Payment Methods - Net Banking
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMethods.savingsAccount" type="String" %}
Payment Methods -  Savings Account
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMethods.currentAccount" type="String" %}
Payment Methods - Current Account
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMethods.prepaidAccount" type="String" %}
Payment Methods - Prepaid Acclount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMethods.bnpl" type="String" %}
Payment Methods -  BNPL
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMethods.creditCards" type="String" %}
Payment Methods - Credit card
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMethods.debitCards" type="String" %}
Payment Methods - Debit card
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMethods.wallet" type="String" %}
Payment Methods - Wallet
{% endswagger-parameter %}

{% swagger-parameter in="header" type="String" required="true" name="X-API-TOKEN " %}
The token got from the 

[login API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/common-apis/get-app-token-api.md)


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

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/mrch-management/v1/merchantDetail'\
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'X-API-TOKEN: token' \
--header 'Content-Type: application/json' \
--data-raw '{
    "merchantId":"1020",
    "merchantName":"TataCliQ",
    "registeredMerchantName":"TataCliQ",
    "businessOwnerName":"tata",
    "altMerchantName":"TataCliQ",
    "businessType":"PARTNERSHIP",
    "userType":"MERCHANT",
    "aggregatorId":"",
    "partnerName1":"",
    "partnerName2":"",
    "merchantCategory":"FASHION",
    "merchantSubCategory":"",
    "mcc":4,
    "shopCode":"",
    "merchantIdRef1":"",
    "merchantIdRef2":"",
    "mobile":"9110780870",
    "altMobile":"",
    "emailId":"gowthami@wibmo.com",
    "altEmailId":"",
    "kycLevel":"1",
    "merchantStatus":"1",
    "addr" :{
        "addressLine1":"NO 45",
        "addressLine2":"Info city",
        "addressLine3":"",
        "city":"chennai",
        "alternateCity":"",
        "state":"Tamilnadu",
        "country":"india",
        "pinCode":"603103"
    },
    "bankInfo":{
        "bankAccountNum":"12345678999",
        "ifscCode":"23456w",
        "supportedCurrency":"IN",
        "supportedDoc":"11",
        "docValidationStatus":"1",
        "merchantVpa":"merchat@vpa",
        "walletId":"1233",
        "accountStatus":"1"
    },
    "merchantKycInfo":{
        "kycDocType":["1","2"],
        "kycIdNum":["1","2"],
        "kycImage":["1","2"],
        "kycStatus":["1","2"],
        "shareCode":["1","2"],
        "gstinNumber":"1234555",
        "gstinValidationStatus":"1"
    },
    "merchantLimit":{
        "dailyLimit":"100",
        "monthlyLimit":"1000",
        "yearlyLimit":"10000",
        "dailyCount":"100",
        "monthlyCount":"1000",
        "yearlyCount":"100000",
        "charges":"0",
        "rebates":"0"
    },
    "paymentInstrument":{
        "staticQr":"1",
        "dynamicQr":"1",
        "paymentLinks":"1",
        "collectPayments":"1",
        "payouts":"1",
        "tapNPay":"1",
        "urlQr":"1"
    },
    "merchantParameters":{
        "bulkQR":"1",
        "financeReq":"1",
        "merchantLink":"1",
        "merchantUrl":"1",
        "monthlySales":"1",
        "langPreference":"1"
    },
    "paymentMethods":{
        "netBanking":"11",
        "savingsAccount":"11",
        "currentAccount":"11",
        "prepaidAccount":"11",
        "bnpl":"11",
        "creditCards":"11",
        "debitCards":"11",
        "wallet":"11"
    }
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "merchantId":"1020",
    "merchantName":"TataCliQ",
    "registeredMerchantName":"TataCliQ",
    "businessOwnerName":"tata",
    "altMerchantName":"TataCliQ",
    "businessType":"PARTNERSHIP",
    "userType":"MERCHANT",
    "aggregatorId":"",
    "partnerName1":"",
    "partnerName2":"",
    "merchantCategory":"FASHION",
    "merchantSubCategory":"",
    "mcc":4,
    "shopCode":"",
    "merchantIdRef1":"",
    "merchantIdRef2":"",
    "mobile":"9110780870",
    "altMobile":"",
    "emailId":"gowthami@wibmo.com",
    "altEmailId":"",
    "kycLevel":"1",
    "merchantStatus":"1",
    "addr" :{
        "addressLine1":"NO 45",
        "addressLine2":"Info city",
        "addressLine3":"",
        "city":"chennai",
        "alternateCity":"",
        "state":"Tamilnadu",
        "country":"india",
        "pinCode":"603103"
    },
    "bankInfo":{
        "bankAccountNum":"12345678999",
        "ifscCode":"23456w",
        "supportedCurrency":"IN",
        "supportedDoc":"11",
        "docValidationStatus":"1",
        "merchantVpa":"merchat@vpa",
        "walletId":"1233",
        "accountStatus":"1"
    },
    "merchantKycInfo":{
        "kycDocType":["1","2"],
        "kycIdNum":["1","2"],
        "kycImage":["1","2"],
        "kycStatus":["1","2"],
        "shareCode":["1","2"],
        "gstinNumber":"1234555",
        "gstinValidationStatus":"1"
    },
    "merchantLimit":{
        "dailyLimit":"100",
        "monthlyLimit":"1000",
        "yearlyLimit":"10000",
        "dailyCount":"100",
        "monthlyCount":"1000",
        "yearlyCount":"100000",
        "charges":"0",
        "rebates":"0"
    },
    "paymentInstrument":{
        "staticQr":"1",
        "dynamicQr":"1",
        "paymentLinks":"1",
        "collectPayments":"1",
        "payouts":"1",
        "tapNPay":"1",
        "urlQr":"1"
    },
    "merchantParameters":{
        "bulkQR":"1",
        "financeReq":"1",
        "merchantLink":"1",
        "merchantUrl":"1",
        "monthlySales":"1",
        "langPreference":"1"
    },
    "paymentMethods":{
        "netBanking":"11",
        "savingsAccount":"11",
        "currentAccount":"11",
        "prepaidAccount":"11",
        "bnpl":"11",
        "creditCards":"11",
        "debitCards":"11",
        "wallet":"11"
    }
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "MER_2000",
    "resDesc": "SUCCESS",
    "data": "1022"
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MER_2000</td><td>SUCCESS</td></tr><tr><td>MER_4004</td><td>Merchant cannot be added</td></tr><tr><td>MER_5000</td><td>Try Later</td></tr><tr><td>MER_4005</td><td>Merchant validation error</td></tr></tbody></table>

## &#x20;
