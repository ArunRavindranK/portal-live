---
description: Provides the list of billers for the given category
---

# Billers List API





{% swagger method="get" path="" baseUrl="<domain>/retail-service/billers/v1/list" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../wallet/wallet-issuance/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../wallet/wallet-issuance/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
will be shared upon onboarding api consumers (clients)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="categoryId" required="true" %}
The category got from the Categories API
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
{% endswagger %}

| Response Body          | Data Type | Field Description                                                                                                                                                                              |
| ---------------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| statusCode             | int       | Success & Failures Codes of the transaction                                                                                                                                                    |
| statusDesc             | String    | Response Description                                                                                                                                                                           |
| billerId               | String    | Unique identifier for a biller                                                                                                                                                                 |
| spId                   | String    | Unique identifier to identify the service provider to connect with                                                                                                                             |
| billerName             | String    | Name of the biller                                                                                                                                                                             |
| fetchOption            | String    | Indicates whether the fetch Option is Mandatory / Optional / Not-Supported                                                                                                                     |
| categoryId             | int       | Unique identifier of the category to which the biller belongs.                                                                                                                                 |
| categoryName           | String    | Name of the category to which the biller belongs (like electricity, gas, etc)                                                                                                                  |
| region                 | String    | Billers that have region specific                                                                                                                                                              |
| regionCode             | String    | Billers that have region code specific                                                                                                                                                         |
| flowType               | String    | Indicates whether BBPS biller or not                                                                                                                                                           |
| state                  | String    | Billers that have state coverage                                                                                                                                                               |
| paymentAmountExactness | String    | Represents allowed payment amount limits that can be paid for a biller where isAdhoc is set as false and fetch option is mandatory. It will take the following values Exact /ExactUp/ExactDown |
| supportDeemed          | Boolean   | Flag indicating whether deemed success is applicable for the biller or not – Yes/No                                                                                                            |
| supportBillValidation  | String    | Indicates whether to call bill validation api provided by the service provider. Currently not used                                                                                             |
| paymentChannels        | String    | Indicates Allowed payment channels for the biller                                                                                                                                              |
| paymentMethods         | String    | Allowed payment modes for the biller                                                                                                                                                           |
| customerParams         | Map       | Indicates the params to pass to service provider                                                                                                                                               |
| active                 | Boolean   | Indicates whether biller is active are not                                                                                                                                                     |
| adhoc                  | Boolean   | Indicates whether the biller supports partial payments. Currently not supported.                                                                                                               |

{% tabs %}
{% tab title="Response" %}


```json
{
  "statusCode": 200,
  "statusDesc": "Success",
  "data": [
    {
      "billerId": "21",
      "spId": "105",
      "billerName": "razorpay",
      "fetchOption": "MANDATORY",
      "categoryId": 2,
      "categoryName": "LOAN",
      "region": "gurgaon",
      "regionCode": "122002",
      "flowType": "BBPS",
      "state": "haryana",
      "paymentAmountExactness": "EXACT_AND_ABOVE",
      "supportDeemed": 0,
      "supportBillValidation": "NOT_SUPPORTED",
      "paymentChannels": [],
      "paymentMethods": [],
      "customerParams": [
        {
          "paramName": "Account ID (RAPDRP) OR Consumer Number / Connection ID (Non-RAPDRP)",
          "optional": 0,
          "dataType": "ALPHANUMERIC",
          "minLength": 0,
          "maxLength": 0,
          "valuesAllowed": null,
          "regex": null,
          "requiredIn": null
        }
      ],
      "customerParam": {
        "paramName": "Account ID (RAPDRP) OR Consumer Number / Connection ID (Non-RAPDRP)",
        "optional": 0,
        "dataType": "ALPHANUMERIC",
        "minLength": 0,
        "maxLength": 0,
        "valuesAllowed": null,
        "regex": null,
        "requiredIn": null
      },
      "active": true,
      "adhoc": false
    },
    {
      "billerId": "AADH00000NATPT",
      "spId": "105",
      "billerName": "Aadhar Housing Finance Limited",
      "fetchOption": "MANDATORY",
      "categoryId": 2,
      "categoryName": "LOAN",
      "region": "IND",
      "regionCode": "IND",
      "flowType": "BBPS",
      "paymentAmountExactness": "EXACT",
      "supportDeemed": 1,
      "supportPendingStatus": "0",
      "supportBillValidation": "NOT_SUPPORTED",
      "billerTimeout": "0",
      "billerMode": "ONLINE",
      "paymentChannels": [],
      "paymentMethods": [],
      "customerParams": [
        {
          "paramName": "Application ID",
          "optional": 0,
          "dataType": "ALPHANUMERIC",
          "minLength": 8,
          "maxLength": 8,
          "valuesAllowed": null,
          "regex": "^[a-zA-Z0-9]+$",
          "requiredIn": null
        }
      ],
      "customerParam": {
        "paramName": "Application ID",
        "optional": 0,
        "dataType": "ALPHANUMERIC",
        "minLength": 8,
        "maxLength": 8,
        "valuesAllowed": null,
        "regex": "^[a-zA-Z0-9]+$",
        "requiredIn": null
      },
      "active": true,
      "adhoc": false
    },
    {
      "billerId": "AAVA00000NATMF",
      "spId": "105",
      "billerName": "AAVAS FINANCIERS LIMITED",
      "fetchOption": "MANDATORY",
      "categoryId": 2,
      "categoryName": "LOAN",
      "region": "India",
      "regionCode": "IND",
      "flowType": "BBPS",
      "state": "India",
      "paymentAmountExactness": "EXACT_AND_BELOW",
      "supportDeemed": 1,
      "supportPendingStatus": "0",
      "supportBillValidation": "NOT_SUPPORTED",
      "billerTimeout": "0",
      "billerMode": "ONLINE",
      "paymentChannels": [],
      "paymentMethods": [],
      "customerParams": [
        {
          "paramName": "Loan no",
          "optional": 0,
          "dataType": "ALPHANUMERIC",
          "minLength": 20,
          "maxLength": 20,
          "valuesAllowed": null,
          "regex": "^[a-zA-Z0-9-]+$",
          "requiredIn": null
        }
      ],
      "customerParam": {
        "paramName": "Loan no",
        "optional": 0,
        "dataType": "ALPHANUMERIC",
        "minLength": 20,
        "maxLength": 20,
        "valuesAllowed": null,
        "regex": "^[a-zA-Z0-9-]+$",
        "requiredIn": null
      },
      "active": true,
      "adhoc": false
    },
    {
      "billerId": "ADAN00000NATO6",
      "spId": "105",
      "billerName": "Adani Capital Pvt Ltd",
      "fetchOption": "MANDATORY",
      "categoryId": 2,
      "categoryName": "LOAN",
      "region": "India",
      "regionCode": "IND",
      "flowType": "BBPS",
      "state": "India",
      "paymentAmountExactness": "EXACT",
      "supportDeemed": 0,
      "supportPendingStatus": "0",
      "supportBillValidation": "NOT_SUPPORTED",
      "billerTimeout": "0",
      "billerMode": "OFFLINEA",
      "paymentChannels": [],
      "paymentMethods": [],
      "customerParams": [
        {
          "paramName": "Loan number",
          "optional": 0,
          "dataType": "ALPHANUMERIC",
          "minLength": 15,
          "maxLength": 15,
          "valuesAllowed": null,
          "regex": "^(\\d{3}[A-Z]{2}|\\d{5}|[A-Z]{5})[A-Z]\\d{9}$",
          "requiredIn": null
        }
      ],
      "customerParam": {
        "paramName": "Loan number",
        "optional": 0,
        "dataType": "ALPHANUMERIC",
        "minLength": 15,
        "maxLength": 15,
        "valuesAllowed": null,
        "regex": "^(\\d{3}[A-Z]{2}|\\d{5}|[A-Z]{5})[A-Z]\\d{9}$",
        "requiredIn": null
      },
      "active": true,
      "adhoc": false
    }
  ]
}
```
{% endtab %}
{% endtabs %}
