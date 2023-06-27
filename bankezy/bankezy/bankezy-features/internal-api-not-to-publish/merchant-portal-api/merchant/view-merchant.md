---
description: Gets the Merchant details for the given Merchant ID
---

# View Merchant

{% swagger method="get" path="/mrch-management/v1/merchantDetail" baseUrl="<domain>" summary="Merchant View api" %}
{% swagger-description %}
This api gets the merchant details for the given merchant id.
{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Merchant-Id" type="int" required="true" %}
Merchant id 
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
curl --location --request GET 'https://user4.pcdev.enstage-sas.com/kong/mrch-management/v1/merchantDetail' \
--header 'Merchant-Id: 1020' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP1-1114' \

```
{% endtab %}

{% tab title="Request sample" %}
```json
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "MER_2000",
    "resDesc": "SUCCESS",
    "data": {
        "merchantId": "1020",
        "merchantName": "TataCliQ",
        "registeredMerchantName": "TataCliQChennai",
        "businessOwnerName": "tata",
        "altMerchantName": "TataCliQ",
        "businessType": "PARTNERSHIP",
        "userType": "MERCHANT",
        "aggregatorId": "",
        "partnerName1": "",
        "partnerName2": "",
        "merchantCategory": "FASHION",
        "merchantSubCategory": "",
        "mcc": 4,
        "shopCode": "",
        "merchantIdRef1": "",
        "merchantIdRef2": "",
        "mobile": "9110780870",
        "altMobile": "",
        "emailId": "gowthami@wibmo.com",
        "altEmailId": "",
        "kycLevel": "1",
        "merchantStatus": "1",
        "addr": {
            "addressLine1": "NO 45",
            "addressLine2": "Info city",
            "addressLine3": "",
            "city": "chennai",
            "alternateCity": "",
            "state": "Tamilnadu",
            "country": "india",
            "pinCode": "603103"
        },
        "bankInfo": {
            "supportedCurrency": "IN",
            "supportedDoc": "11",
            "docValidationStatus": "1",
            "accountStatus": "1",
            "bankAccountNum": "12345678999",
            "ifscCode": "23456w",
            "merchantVpa": "merchat@vpa",
            "walletId": "11"
        },
        "merchantKycInfo": {
            "merchantId": "1020",
            "kycDocType": [
                "1",
                "2"
            ],
            "kycIdNum": [
                "1",
                "2"
            ],
            "kycImage": [
                "1",
                "2"
            ],
            "kycStatus": [
                "1",
                "2"
            ],
            "shareCode": [
                "1",
                "2"
            ],
            "gstinNumber": "1234555",
            "gstinValidationStatus": "1"
        },
        "merchantLimit": {
            "dailyLimit": "100",
            "monthlyLimit": "1000",
            "yearlyLimit": "10000",
            "dailyCount": "100",
            "monthlyCount": "1000",
            "yearlyCount": "100000",
            "charges": "0",
            "rebates": "0"
        },
        "paymentInstrument": {
            "staticQr": "1",
            "dynamicQr": "1",
            "paymentLinks": "1",
            "collectPayments": "1",
            "payouts": "1",
            "tapNPay": "1",
            "urlQr": "1"
        },
        "merchantParameters": {
            "bulkQR": "1",
            "financeReq": "1",
            "merchantLink": "1",
            "merchantUrl": "1",
            "monthlySales": "1",
            "langPreference": "1"
        },
        "paymentMethods": {
            "netBanking": "11",
            "savingsAccount": "112",
            "currentAccount": "112",
            "prepaidAccount": "113",
            "bnpl": "114",
            "creditCards": "115",
            "debitCards": "11",
            "wallet": "11"
        }
    }
}

```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MER_2000</td><td>SUCCESS</td></tr><tr><td>MER_4001</td><td>Merchant Info Not Available</td></tr><tr><td>MER_5000</td><td>Try Later</td></tr></tbody></table>

## &#x20;
