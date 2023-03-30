---
description: To fetch the amount to be paid by customer
---

# Bill Fetch API

{% swagger method="post" path="/" baseUrl="<domain>/retail-service/bill/v1/billpay/billfetch" summary="To fetch the amount to be paid by customer" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="BillerId" type="String" required="true" %}
Unique identifier for a biller
{% endswagger-parameter %}

{% swagger-parameter in="body" name="appName" type="String" required="true" %}
Name of the APP
{% endswagger-parameter %}

{% swagger-parameter in="body" name="imeiNumber " type="String" required="true" %}
Initiating channel IMEI Number
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the

[Get Token API](../../market-place/api-specification/get-token-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
will be shared upon onboarding api consumers (clients)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="initiatingChannel " type="String" required="true" %}
Initiating name of the channel
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ipAddress" type="String" required="true" %}
IP Address of request initiating channel
{% endswagger-parameter %}

{% swagger-parameter in="body" name="osName" type="String" required="true" %}
OS of request initiating channel
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerParams " type="Map<String,String>" required="true" %}
Unique parameters of the biller
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerEmailId" type="String" required="false" %}
EmailId of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerMobileNumber " required="true" type="String" %}
User logged in mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName " type="String" required="false" %}
Name of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="categoryId" type="Int" required="true" %}
Unique id of the category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="operatorCode" type="String" required="false" %}
Short Name of the operator
{% endswagger-parameter %}

{% swagger-parameter in="body" name="operatorName" type="String" required="false" %}
Name of the operator
{% endswagger-parameter %}

{% swagger-parameter in="body" name="serviceId" type="Int" required="false" %}
service Id belongs to category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transactionRefId" type="String" required="false" %}
Unique Reference Id generated for the transaction
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

| Response Body     | Data Type | Field Description                                                                                                                                                                                      |
| ----------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| statusCode        | int       | Success & Failure status code of the transactions                                                                                                                                                      |
| statusDesc        | String    | Response Description                                                                                                                                                                                   |
| refId             | String    | Unique reference number for the transaction                                                                                                                                                            |
| requestTimeStamp  | String    | Date and time of transaction                                                                                                                                                                           |
| amount            | String    | Fetch amount for the customer                                                                                                                                                                          |
| accountHolderName | String    | Name of the customer on whom bill was generated against                                                                                                                                                |
| dueDate           | String    | Due date for the bill payment                                                                                                                                                                          |
| billDate          | String    | Bill generated date                                                                                                                                                                                    |
| billerId          | String    | Unique identifier for the biller                                                                                                                                                                       |
| amountDetails     | String    | Total Amount Breakup (It may be available or may not be available).It will contain breakup details of total payable amount. E.g. for education category :- { "Bus fee":"100", "education fees":"100" } |
| additionalParams  | Array     | Additional fields related to billers.If any available otherwise it will be null.                                                                                                                       |
| billNumber        | String    | Unique number of the biller                                                                                                                                                                            |
| billPeriod        | Boolean   | Service Provider Bill Preiod for Mobile Number                                                                                                                                                         |
| approvalRefNum    | String    | Service Provider Bill fetch Reference number                                                                                                                                                           |

{% tabs %}
{% tab title="sample curl  Request" %}
```json
curl --location --request POST 'https://app9.pcdev.enstage-sas.com/retail-service/bill/v1/billpay/billfetch' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \
--header 'Content-Type: application/json' \
--header 'X-API-KEY: MOB-APP-2001' \
-data-raw '{
    "billerId": "BHIM00000NAT21",
    "categoryId": 7,
    "customerParams": {
        "Mobile Number": "9848391094"
    },
    "deviceDetails": {
        "appName": "BankEzy",
        "imeiNumber": "54-E1-AD-27-FE-E3",
        "initiatingChannel": "MOB",
        "ipAddress": "127.0.0.1",
        "osName": "Android"
    },
    "operatorCode": "VF",
    "operatorName": "VODAFONE",
    "serviceId": 2,
    "transactionRefId": "",
    "userDetails": {
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
    "billerId": "BHIM00000NAT21",
    "categoryId": 7,
    "customerParams": {
        "Mobile Number": "9848391094"
    },
    "deviceDetails": {
        "appName": "BankEzy",
        "imeiNumber": "54-E1-AD-27-FE-E3",
        "initiatingChannel": "MOB",
        "ipAddress": "127.0.0.1",
        "osName": "Android"
    },
    "operatorCode": "VF",
    "operatorName": "VODAFONE",
    "serviceId": 2,
    "transactionRefId": "",
    "userDetails": {
        "customerEmailId": "gowthamiavula9@gmail.com",
        "customerMobileNumber": "9848391094",
        "customerName": "Gowthami Avula"
    }
}
```
{% endtab %}

{% tab title="Response Example" %}
```json
{
    "statusCode": 200,
    "statusDesc": "Success",
    "data": {
        "refId": "11111209351039592738321176789748404",
        "requestTimeStamp": "2022-03-16",
        "amount": 265120.0,
        "accountHolderName": "Mr.Suresh",
        "dueDate": "2022-03-26",
        "billDate": "2022-03-11",
        "billerId": "TATAPWR00DEL01",
        "amountDetails": null,
        "additionalParams": {},
        "billNumber": "010207974309",
        "billPeriod": "03",
        "approvalRefNum": "BUGBX991"
        }
}
```
{% endtab %}
{% endtabs %}
