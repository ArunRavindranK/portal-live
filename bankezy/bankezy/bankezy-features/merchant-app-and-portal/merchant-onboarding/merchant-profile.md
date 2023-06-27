---
description: Get the Merchant Profile associated with the Mobile Number
---

# Merchant Profile

{% swagger method="get" path="/mrch-management/v1/merchantinfo'" baseUrl="<domain>" summary="Merchant Profile" %}
{% swagger-description %}
This api used to get the merchant details based on Mobile Number.
{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" type="String" %}
MOB-APP-1114
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN " type="String" required="true" %}
The token got from the login API
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
curl --location --request GET 'https://user4.pcdev.enstage-sas.com/kong/mrch-management/v1/merchantinfo' \
--header 'X-API-KEY: MOB-APP1-1114' \
--header 'X-ACCOUNT-NUMBER: '1814' \

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
        "merchantId": "1001",
        "merchantName": "MERCHANT1",
        "registeredMerchantName": "DFS MERCHANT",
        "businessType": "PARTNERSHIP",
        "partnerName1": null,
        "partnerName2": null,
        "merchantCategory": "FASHION",
        "mobile": "8754429068",
        "userType": "MERCHANT",
        "addressLine1": "no 13, jasper",
        "addressLine2": "hiranandani",
        "addressLine3": null,
        "city": "Chennai",
        "state": "Tamilnadu",
        "country": "India",
        "bankAccountNum": "130023456789",
        "ifscCode": "1234",
        "merchantVpa": "merchant1@upi",
        "walletId": "1234567812",
        "mcc": 5611,
        "pinCode": "600113",
        "limit": null,
        "userAlert": {
            "sms": "1",
            "email": "1",
            "push": "1",
            "sticky": "0",
            "voiceAlert": "1",
            "speaker": "0"
        },
        "merchantStatus": null,
        "kycDocType": null,
        "kycIdNum": null,
        "kycStatus": null,
        "gstinNumber": null
    }
}
```
{% endtab %}
{% endtabs %}

## Custom response codes

<table><thead><tr><th width="373">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>MER_2000</td><td>SUCCESS</td></tr><tr><td>MER_4001</td><td>Merchant Info Not Available</td></tr><tr><td>MER_5000</td><td>Try_Later</td></tr></tbody></table>

## &#x20;
