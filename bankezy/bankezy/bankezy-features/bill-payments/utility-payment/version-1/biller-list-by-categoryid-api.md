---
description: To provide billers for the seleted category
---

# Biller list By CategoryId API

{% swagger method="get" path="" baseUrl="<domain>/retail-service/billers/v1/list?categoryId=?" summary="To provide availiable billers for the given category" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

## Response Details

| Response Body          | Data Type | Field Description                                                                                                                                                                              |
| ---------------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| statusCode             | int       | Status of transaction                                                                                                                                                                          |
| statusDesc             | String    | Response Description                                                                                                                                                                           |
| billerId               | String    | Unique identifier for a biller                                                                                                                                                                 |
| spId                   | String    | Unique identifier to identify the service provider to connect with                                                                                                                             |
| billerName             | String    | Name of the biller                                                                                                                                                                             |
| fetchOption            | String    | Indicates whether the fetch Option is Mandatory / Optional / Not-Supported                                                                                                                     |
| categoryId             | int       | Unique identifier of the category to which the biller belongs.                                                                                                                                 |
| categoryName           | String    | Name of the category to which the biller belongs (like electricity, gas, etc)                                                                                                                  |
| region                 | String    | Billers that have region specific                                                                                                                                                              |
| regionCode             | String    | Billers that have region code specific                                                                                                                                                         |
| flowType               | String    | Indicates whether BBPS biller or no                                                                                                                                                            |
| state                  | String    | Billers that have state coverage                                                                                                                                                               |
| paymentAmountExactness | String    | Represents allowed payment amount limits that can be paid for a biller where isAdhoc is set as false and fetch option is mandatory. It will take the following values Exact /ExactUp/ExactDown |
| supportDeemed          | Boolean   | Flag indicating whether deemed success is applicable for the biller or not – Yes/No                                                                                                            |
| supportBillValidation  | String    | Indicates whether to call bill validation api provided by the service provider. Currently not used                                                                                             |
| paymentChannels        | String    | Allowed payment modes for the biller                                                                                                                                                           |
| paymentMethods         | String    | Allowed payment modes for the biller                                                                                                                                                           |
| customerParams         | Map       | Indicates the params to pass to service provider                                                                                                                                               |
| active                 | Boolean   | Indicates whether biller is active are not                                                                                                                                                     |
| adhoc                  | Boolean   | Indicates whether the biller supports partial payments. Currently not supported.                                                                                                               |

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request GET 'https://app9.pcdev.enstage-sas.com/retail-service/billers/v1/list?categoryId=13' \
--header 'X-PROGRAM-ID: 1111' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \
--header 'Content-Type: text/plain' \
--header 'X-API-KEY: MOB-APP-1111' \
--data-raw ''
```
{% endtab %}

{% tab title="Response Example" %}


```json
{
    "statusCode": 200,
    "statusDesc": "Success",
    "data": [
        {
            "billerId": "AirtelPREPAID",
            "spId": "105",
            "billerName": "AIRTEL",
            "fetchOption": "NOT_SUPPORTED",
            "categoryId": 13,
            "categoryName": "MOBILE PREPAID",
            "region": "IND",
            "regionCode": "IND",
            "flowType": "NON-BBPS",
            "supportDeemed": 0,
            "supportPendingStatus": "0",
            "supportBillValidation": "OPTIONAL",
            "billerTimeout": "0",
            "billerMode": "ONLINE",
            "paymentChannels": [
                {
                    "paymentMode": "MOB",
                    "minLimit": 4.0,
                    "maxLimit": 15000.0
                },
                {
                    "paymentMode": "INT",
                    "minLimit": null,
                    "maxLimit": 15000.0
                }
            ],
            "paymentMethods": [
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                }
            ],
            "customerParams": [
                {
                    "paramName": "MobileNumber",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 10,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "CircleRefID",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "OperatorCode",
                    "optional": 0,
                    "dataType": "ALPHANUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                }
            ],
            "customerParam": {
                "paramName": "MobileNumber",
                "optional": 0,
                "dataType": "NUMERIC",
                "minLength": 10,
                "maxLength": 10,
                "valuesAllowed": null,
                "regex": null,
                "requiredIn": "payment"
            },
            "active": true,
            "adhoc": false
        },
        {
            "billerId": "BSNLPREPAID",
            "spId": "105",
            "billerName": "BSNL",
            "fetchOption": "NOT_SUPPORTED",
            "categoryId": 13,
            "categoryName": "MOBILE PREPAID",
            "region": "IND",
            "regionCode": "IND",
            "flowType": "NON-BBPS",
            "state": "India",
            "supportDeemed": 0,
            "supportPendingStatus": "0",
            "supportBillValidation": "OPTIONAL",
            "billerTimeout": "0",
            "billerMode": "ONLINE",
            "paymentChannels": [
                {
                    "paymentMode": "MOB",
                    "minLimit": 4.0,
                    "maxLimit": 15000.0
                },
                {
                    "paymentMode": "INT",
                    "minLimit": null,
                    "maxLimit": 15000.0
                }
            ],
            "paymentMethods": [
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                }
            ],
            "customerParams": [
                {
                    "paramName": "MobileNumber",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 10,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "CircleRefID",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "OperatorCode",
                    "optional": 0,
                    "dataType": "ALPHANUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "RechargeType",
                    "optional": 1,
                    "dataType": "ALPHANUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                }
            ],
            "customerParam": {
                "paramName": "MobileNumber",
                "optional": 0,
                "dataType": "NUMERIC",
                "minLength": 10,
                "maxLength": 10,
                "valuesAllowed": null,
                "regex": null,
                "requiredIn": "payment"
            },
            "active": true,
            "adhoc": false
        },
        {
            "billerId": "IDEAPREPAID",
            "spId": "105",
            "billerName": "IDEA",
            "fetchOption": "NOT_SUPPORTED",
            "categoryId": 13,
            "categoryName": "MOBILE PREPAID",
            "region": "IND",
            "flowType": "NON-BBPS",
            "supportDeemed": 0,
            "supportPendingStatus": "0",
            "supportBillValidation": "OPTIONAL",
            "billerTimeout": "0",
            "billerMode": "ONLINE",
            "paymentChannels": [
                {
                    "paymentMode": "MOB",
                    "minLimit": 4.0,
                    "maxLimit": 15000.0
                },
                {
                    "paymentMode": "INT",
                    "minLimit": 4.0,
                    "maxLimit": 15000.0
                }
            ],
            "paymentMethods": [
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                }
            ],
            "customerParams": [
                {
                    "paramName": "MobileNumber",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 10,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "CircleRefID",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "OperatorCode",
                    "optional": 0,
                    "dataType": "ALPHANUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                }
            ],
            "customerParam": {
                "paramName": "MobileNumber",
                "optional": 0,
                "dataType": "NUMERIC",
                "minLength": 10,
                "maxLength": 10,
                "valuesAllowed": null,
                "regex": null,
                "requiredIn": "payment"
            },
            "active": true,
            "adhoc": false
        },
        {
            "billerId": "JioPREPAID",
            "spId": "105",
            "billerName": "RELIANCE JIO",
            "fetchOption": "NOT_SUPPORTED",
            "categoryId": 13,
            "categoryName": "MOBILE PREPAID",
            "region": "IND",
            "flowType": "NON-BBPS",
            "supportDeemed": 0,
            "supportPendingStatus": "0",
            "supportBillValidation": "OPTIONAL",
            "billerTimeout": "0",
            "billerMode": "ONLINE",
            "paymentChannels": [
                {
                    "paymentMode": "MOB",
                    "minLimit": 4.0,
                    "maxLimit": 15000.0
                },
                {
                    "paymentMode": "INT",
                    "minLimit": null,
                    "maxLimit": 15000.0
                }
            ],
            "paymentMethods": [
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                }
            ],
            "customerParams": [
                {
                    "paramName": "MobileNumber",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 10,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "CircleRefID",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "OperatorCode",
                    "optional": 0,
                    "dataType": "ALPHANUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                }
            ],
            "customerParam": {
                "paramName": "MobileNumber",
                "optional": 0,
                "dataType": "NUMERIC",
                "minLength": 10,
                "maxLength": 10,
                "valuesAllowed": null,
                "regex": null,
                "requiredIn": "payment"
            },
            "active": true,
            "adhoc": false
        },
        {
            "billerId": "MTNLPREPAID",
            "spId": "105",
            "billerName": "MTNL",
            "fetchOption": "NOT_SUPPORTED",
            "categoryId": 13,
            "categoryName": "MOBILE PREPAID",
            "region": "IND",
            "regionCode": "IND",
            "flowType": "NON-BBPS",
            "state": "India",
            "supportDeemed": 0,
            "supportPendingStatus": "0",
            "supportBillValidation": "OPTIONAL",
            "billerTimeout": "0",
            "billerMode": "ONLINE",
            "paymentChannels": [
                {
                    "paymentMode": "MOB",
                    "minLimit": 4.0,
                    "maxLimit": 15000.0
                },
                {
                    "paymentMode": "INT",
                    "minLimit": null,
                    "maxLimit": 15000.0
                }
            ],
            "paymentMethods": [
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                }
            ],
            "customerParams": [
                {
                    "paramName": "MobileNumber",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 10,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "CircleRefID",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "OperatorCode",
                    "optional": 0,
                    "dataType": "ALPHANUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "RechargeType",
                    "optional": 1,
                    "dataType": "ALPHANUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                }
            ],
            "customerParam": {
                "paramName": "MobileNumber",
                "optional": 0,
                "dataType": "NUMERIC",
                "minLength": 10,
                "maxLength": 10,
                "valuesAllowed": null,
                "regex": null,
                "requiredIn": "payment"
            },
            "active": true,
            "adhoc": false
        },
        {
            "billerId": "VODAFONEPREPAID",
            "spId": "105",
            "billerName": "VODAFONE",
            "fetchOption": "NOT_SUPPORTED",
            "categoryId": 13,
            "categoryName": "MOBILE PREPAID",
            "region": "IND",
            "flowType": "NON-BBPS",
            "supportDeemed": 0,
            "supportPendingStatus": "0",
            "supportBillValidation": "OPTIONAL",
            "billerTimeout": "0",
            "billerMode": "ONLINE",
            "paymentChannels": [
                {
                    "paymentMode": "MOB",
                    "minLimit": 4.0,
                    "maxLimit": 15000.0
                },
                {
                    "paymentMode": "INT",
                    "minLimit": null,
                    "maxLimit": 15000.0
                }
            ],
            "paymentMethods": [
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                },
                {
                    "paymentMethod": null,
                    "minLimit": 4.0,
                    "autopayAllowed": null,
                    "paylaterAllowed": null,
                    "maxLimit": null,
                    "paymentMethodCategory": null
                }
            ],
            "customerParams": [
                {
                    "paramName": "MobileNumber",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 10,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "CircleRefID",
                    "optional": 0,
                    "dataType": "NUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                },
                {
                    "paramName": "OperatorCode",
                    "optional": 0,
                    "dataType": "ALPHANUMERIC",
                    "minLength": 1,
                    "maxLength": 10,
                    "valuesAllowed": null,
                    "regex": null,
                    "requiredIn": "payment"
                }
            ],
            "customerParam": {
                "paramName": "MobileNumber",
                "optional": 0,
                "dataType": "NUMERIC",
                "minLength": 10,
                "maxLength": 10,
                "valuesAllowed": null,
                "regex": null,
                "requiredIn": "payment"
            },
            "active": true,
            "adhoc": false
        }
    ]
}
```
{% endtab %}
{% endtabs %}
