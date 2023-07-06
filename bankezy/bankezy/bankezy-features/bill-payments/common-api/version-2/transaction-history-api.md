# Transaction History API

{% swagger method="post" path="" baseUrl="<domain>/retail-service/recharge/v2/transaction/history" summary="To display the recent transactions for mobile number" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
 token got from the 

[Get Token API](../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
will be shared upon onboarding api consumers (clients)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="CONTENT-TYPE" required="true" %}
text/plain
{% endswagger-parameter %}

{% swagger-parameter in="body" name="categoryId" required="true" %}
Unique identifier for the category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerMobileNumber" required="true" %}
Customer logged in Mobile Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="limit" %}
Number of records to be fetched
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantAccountNo" %}
Unique merchant Account Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="offset" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="serviceId" required="true" %}
Indicates the service request type like Prepaid, postpaid, DTH etc
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

{% tabs %}
{% tab title="sample curl  Request" %}
```json
curl --location --request POST 'https://app9.pcdev.enstage-sas.com/retail-service/recharge/v2/transaction/history' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'Content-Type: text/plain' \
--data-raw '{
  "categoryId": 13,
  "customerMobileNumber": "8892239899",
  "limit": 10,
  "merchantAccountNo": "",
  "offset": 0,
  "serviceId": [
    1
  ]
}'
```


{% endtab %}

{% tab title="Request Example" %}
```json
{
  "categoryId": 13,
  "customerMobileNumber": "8892239899",
  "limit": 10,
  "merchantAccountNo": "",
  "offset": 0,
  "serviceId": [
    1
  ]
}
```


{% endtab %}

{% tab title="Response Example" %}
```json
{
    "responseTimeTakenMs": 0,
    "resCode": "RTL200",
    "resDesc": "Success",
    "dataList": [
        {
            "actionData": "9843564706",
            "operatorPrefix": "IDEA",
            "billerName": "IC",
            "serviceId": 1,
            "serviceName": "Mobile Prepaid Recharge",
            "rechargeType": "TOPUP",
            "subscriberName": "New Number",
            "amount": 1800.0,
            "transactionDate": "2022-06-17 11:43:26",
            "customerParams": {
                "MobileNumber": "9843564706",
                "CircleRefID": "2",
                "OperatorCode": "IDEA"
            },
            "billerID": "IDEAPREPAID",
            "categoryName": "IC",
            "categoryId": 13,
            "circle_RefId": 2
        },
        {
            "actionData": "9843564706",
            "operatorPrefix": "IDEA",
            "billerName": "IC",
            "serviceId": 1,
            "serviceName": "Mobile Prepaid Recharge",
            "rechargeType": "TOPUP",
            "subscriberName": "New Number",
            "amount": 1800.0,
            "transactionDate": "2022-06-20 13:40:27",
            "customerParams": {
                "MobileNumber": "9843564706",
                "CircleRefID": "0",
                "OperatorCode": "IDEA"
            },
            "billerID": "IDEAPREPAID",
            "categoryName": "IC",
            "categoryId": 13,
            "circle_RefId": 0
        }
    ]
}
```


{% endtab %}
{% endtabs %}

**Response Codes**

| Response Body   | Data Type | Field Description                                                                                                                                                                              |
| --------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| resCode         | String    | Status of transaction                                                                                                                                                                          |
| resDesc         | String    | Response Description                                                                                                                                                                           |
| billerID        | String    | Unique identifier for a biller                                                                                                                                                                 |
| actionData      | String    | Unique identifier to identify the service provider to connect with                                                                                                                             |
| operatorPrefix  | String    | Name of the biller                                                                                                                                                                             |
| billerName      | String    | Indicates whether the fetch Option is Mandatory / Optional / Not-Supported                                                                                                                     |
| serviceId       | int       | Unique identifier of the category to which the biller belongs.                                                                                                                                 |
| serviceName     | String    | Name of the category to which the biller belongs (like electricity, gas, etc)                                                                                                                  |
| rechargeType    | String    | Billers that have region specific                                                                                                                                                              |
| subscriberName  | String    | Billers that have region code specific                                                                                                                                                         |
| amount          | Double    | Indicates whether BBPS biller or no                                                                                                                                                            |
| transactionDate | String    | Billers that have state coverage                                                                                                                                                               |
| customerParams  | String    | Represents allowed payment amount limits that can be paid for a biller where isAdhoc is set as false and fetch option is mandatory. It will take the following values Exact /ExactUp/ExactDown |
| categoryName    | String    | Flag indicating whether deemed success is applicable for the biller or not – Yes/No                                                                                                            |
| categoryId      | Integer   | Indicates whether to call bill validation api provided by the service provider. Currently not used                                                                                             |
| circle\_RefId   | Integer   | Allowed payment modes for the biller                                                                                                                                                           |

**Custom Respone Codes**

<table><thead><tr><th width="276">Response Codes</th><th>Response Description</th></tr></thead><tbody><tr><td>RTL012</td><td>Invalid data</td></tr><tr><td>RTL013</td><td>No Records found for given transaction reference Number</td></tr><tr><td>RTL200</td><td>Success</td></tr><tr><td>RTL006</td><td>Internal Error</td></tr></tbody></table>
