---
description: Verify the request with biller aggregator (or) service provider
---

# Payment Validation API

{% swagger method="post" path="" baseUrl="<domain>/retail-service/validation/v1/paymentValidation" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[Get Token API](../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
will be shared upon onboarding api consumers (clients)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" required="true" %}
Transaction Amount
{% endswagger-parameter %}

{% swagger-parameter in="body" name="billerId" %}
Unique identifier of the biller
{% endswagger-parameter %}

{% swagger-parameter in="body" name="categoryId" required="true" type="Int" %}
Unique identifier of the category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="circleRefId" type="Int" %}
To specify the circle Id of the Mobile Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" %}
Region name of the biller
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerParams" type="Map<String,String>" required="true" %}
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

## Response Details

| Response Body    | Data Type | Field Description                         |
| ---------------- | --------- | ----------------------------------------- |
| statusCode       | int       | Success & Failure code of the transaction |
| statusDesc       | String    | Response Description                      |
| transactionRefId | String    | Unique transaction reference ID.          |
| billerId         | String    | Unique Id for the biller                  |

{% tabs %}
{% tab title="Sample Curl Example" %}
```json
curl --location --request POST 'https://app9.pcdev.enstage-sas.com/retail-service/validation/v1/paymentValidation' \
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
}s
```
{% endtab %}

{% tab title="Response Example" %}
```json
{
    "statusCode": 200,
    "statusDesc": "Success",
    "data": {
        "transactionRefId": "11111209351039592738321176789748650",
        "billerId": "VODAFONEPREPAID"
    }
}
```
{% endtab %}
{% endtabs %}
