---
description: >-
  Validates the bill payment request so that during actual submit there is no
  failure
---

# Validation Init API

{% swagger method="post" path="" baseUrl="<domain>retail-service/validation/v1/init" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" type="String" %}
The token got from the 

[Get Token API](../../market-place/api-specification/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" type="String" %}
will be shared upon onboarding api consumers (clients)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" required="true" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="billerId" %}
Unique identifier of the biller
{% endswagger-parameter %}

{% swagger-parameter in="body" name="categoryId" type="Int" required="true" %}
Unique identifier of the category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="circleRefId" type="int" %}
To specify the circle Id of the Mobile Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" %}
Region name of the biller
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currencyCode" %}
Region currency of the biller
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerParams" required="true" type="Map<String,String>" %}
Unique parameters of the biller
{% endswagger-parameter %}

{% swagger-parameter in="body" name="appName" required="true" %}
Name of the app
{% endswagger-parameter %}

{% swagger-parameter in="body" name="imeiNumber" required="true" %}
**I**

nitiating channel IMEI Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="initiatingChannel" required="true" %}
Initiating name of the channel
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ipAddress" required="true" %}
IP Address of request initiating channel
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osName" required="true" %}
OS of request initiating channel
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantAccountNo" required="true" %}
Merchant Number for BankEzy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="operatorName" %}
Name of the mobile operator
{% endswagger-parameter %}

{% swagger-parameter in="body" name="operatorPrefix" %}
Prefix of the mobile operator
{% endswagger-parameter %}

{% swagger-parameter in="body" name="rechargeType" %}
Type of the recharge for mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="retailReferenceId" required="true" %}
Unique Reference Id generated for the transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="serviceId" %}
Service id of the category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="subscriberName" %}
Name of the subscriber
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerEmailId" %}
EmailId of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerMobileNumber" required="true" %}
User logged in mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" %}
Name of the customer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="CONTENT-TYPE" required="true" %}
text/plain
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
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
{% endswagger %}

| Response Body       | Data Type | Field Description                                 |
| ------------------- | --------- | ------------------------------------------------- |
| statusCode          | int       | Success & Failure status codes of the transaction |
| statusDesc          | String    | Response Description                              |
| transactionRefId    | String    | Unique transaction reference number               |
| merchantId          | String    | Unique identifier of the merchant onboarded       |
| merchantName        | String    | Name of the merchant                              |
| merchantCountryCode | String    | Country code of merchant onboarded                |
| merchantAppId       | String    | AppId of the merchant                             |
| billerId            | String    | Unique identifier of the biller                   |

{% tabs %}
{% tab title="sample curl  Request " %}
```json
curl --location --request POST 'https://app9.pcdev.enstage-sas.com/retail-service/validation/v1/init' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \
--header 'Content-Type: text/plain' \
--header 'X-API-KEY: MOB-APP-2001' \
--data-raw '{
    "amount": 99.0,
    "billerId": "VODAFONEPREPAID",
    "categoryId": 7,
    "circleRefId": 17,
    "countryCode": "IN",
    "currencyCode": "356",
    "customerParams": {
        "MobileNumber": "9843564706",
        "CircleRefID": "17",
        "OperatorCode": "VF"
    },
    "deviceDetails": {
        "appName": "BANKZY",
        "imeiNumber": "0aef07f0d803f706",
        "initiatingChannel": "MOB",
        "ipAddress": "127.0.0.1",
        "osName": "Android"
    },
    "merchantAccountNo": "1834",
    "operatorName": "VODAFONE",
    "operatorPrefix": "VF",
    "rechargeType": "rc-post",
    "retailReferenceId": "11111209351039592738321176789748650",
    "serviceId": 2,
    "subscriberName": "Gowthami Avula",
    "userParams": {
        "customerEmailId": "gowthamiavula9@gmail.com",
        "customerMobileNumber": "9848391094",
        "customerName": "Gowthami Avula"
    }
}'
```
{% endtab %}

{% tab title="Request Example" %}
```json
{
    "amount": 99.0,
    "billerId": "VODAFONEPREPAID",
    "categoryId": 7,
    "circleRefId": 17,
    "countryCode": "IN",
    "currencyCode": "356",
    "customerParams": {
        "MobileNumber": "9843564706",
        "CircleRefID": "17",
        "OperatorCode": "VF"
    },
    "deviceDetails": {
        "appName": "BANKZY",
        "imeiNumber": "0aef07f0d803f706",
        "initiatingChannel": "MOB",
        "ipAddress": "127.0.0.1",
        "osName": "Android"
    },
    "merchantAccountNo": "1834",
    "operatorName": "VODAFONE",
    "operatorPrefix": "VF",
    "rechargeType": "rc-post",
    "retailReferenceId": "11111209351039592738321176789748650",
    "serviceId": 2,
    "subscriberName": "Gowthami Avula",
    "userParams": {
        "customerEmailId": "gowthamiavula9@gmail.com",
        "customerMobileNumber": "9848391094",
        "customerName": "Gowthami Avula"
    }
}curl --location --request POST 'https://app9.pcdev.enstage-sas.com/retail-service/validation/v1/init' \
--header 'X-PROGRAM-ID: 1111' \
--header 'Content-Type: application/json' \
--data-raw '{
    "amount": 99.0,
    "billerId": "VODAFONEPREPAID",
    "categoryId": 7,
    "circleRefId": 17,
    "countryCode": "IN",
    "currencyCode": "356",
    "customerParams": {
        "MobileNumber": "9843564706",
        "CircleRefID": "17",
        "OperatorCode": "VF"
    },
    "deviceDetails": {
        "appName": "BANKZY",
        "imeiNumber": "0aef07f0d803f706",
        "initiatingChannel": "MOB",
        "ipAddress": "127.0.0.1",
        "osName": "Android"
    },
    "merchantAccountNo": "1834",
    "operatorName": "VODAFONE",
    "operatorPrefix": "VF",
    "rechargeType": "rc-post",
    "retailReferenceId": "11111209351039592738321176789748650",
    "serviceId": 2,
    "subscriberName": "Gowthami Avula",
    "userParams": {
        "customerEmailId": "gowthamiavula9@gmail.com",
        "customerMobileNumber": "9848391094",
        "customerName": "Gowthami Avula"
    }
}'
```
{% endtab %}

{% tab title="Response Example" %}
```json
{
    "statusCode": 200,
    "statusDesc": "Success",
    "data": {
        "merchantDetails": {
            "merchantId": "81516121",
            "merchantName": "Test Merchant",
            "merchantCountryCode": "IN",
            "merchantAppId": "7900"
        },
        "transactionRefId": "11111209351039592738321176789748650",
        "billerId": "VODAFONEPREPAID"
    }
}
```
{% endtab %}
{% endtabs %}
