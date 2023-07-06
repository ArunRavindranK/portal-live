---
description: To fetch list of circles
---

# Circle List API

{% swagger method="get" path="retail-service/home/circle/list/v1" baseUrl="<domain>" summary="To fetch list of circles" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[Get Token API](../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
will be shared upon onboarding api consumers (clients)
{% endswagger-parameter %}
{% endswagger %}

## Response Details

| Response Body | Data Type | Filed Description                        |
| ------------- | --------- | ---------------------------------------- |
| statusCode    | int       | Status of transaction                    |
| statusDesc    | String    | Response Description                     |
| circleId      | int       | Id indicating the region of the operator |
| circleName    | String    | Region of the operator                   |
| status        | Boolean   | Indicates status of the circle           |

{% tabs %}
{% tab title="sample curl  Request" %}
```json
curl --location --request GET 'https://app9.pcdev.enstage-sas.com/retail-service/home/circle/list/v1' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \
--header 'X-API-KEY: MOB-APP-2001'
```


{% endtab %}

{% tab title="Response Example" %}
```json
{
    "statusCode": 200,
    "statusDesc": "Success",
    "data": [
        {
            "circleId": 1,
            "circleName": "WEST BENGAL",
            "status": 1
        },
        {
            "circleId": 2,
            "circleName": "ANDHRA PRADESH AND TELANGNA",
            "status": 1
        },
        {
            "circleId": 3,
            "circleName": "ASSAM",
            "status": 1
        },
        {
            "circleId": 5,
            "circleName": "GUJARAT",
            "status": 1
        },
        {
            "circleId": 6,
            "circleName": "HARYANA",
            "status": 1
        },
        {
            "circleId": 7,
            "circleName": "HIMACHAL PRADESH",
            "status": 1
        },
        {
            "circleId": 8,
            "circleName": "JAMMU AND KASHMIR",
            "status": 1
        },
        {
            "circleId": 9,
            "circleName": "KARNATAKA",
            "status": 1
        },
        {
            "circleId": 10,
            "circleName": "KERALA",
            "status": 1
        },
        {
            "circleId": 11,
            "circleName": "MADHYA PRADESH AND CHATTISGARH",
            "status": 1
        },
        {
            "circleId": 12,
            "circleName": "MAHARASHTRA AND GOA",
            "status": 1
        },
        {
            "circleId": 13,
            "circleName": "NORTH EAST",
            "status": 1
        },
        {
            "circleId": 14,
            "circleName": "ODISHA",
            "status": 1
        },
        {
            "circleId": 15,
            "circleName": "PUNJAB",
            "status": 1
        },
        {
            "circleId": 16,
            "circleName": "RAJASTHAN",
            "status": 1
        },
        {
            "circleId": 17,
            "circleName": "TAMIL NADU",
            "status": 1
        },
        {
            "circleId": 18,
            "circleName": "UTTAR PRADESH WEST AND UTTARAKHAND",
            "status": 1
        },
        {
            "circleId": 19,
            "circleName": "UTTAR PRADESH EAST",
            "status": 1
        },
        {
            "circleId": 20,
            "circleName": "CHENNAI",
            "status": 1
        },
        {
            "circleId": 21,
            "circleName": "DELHI AND NCR",
            "status": 1
        },
        {
            "circleId": 22,
            "circleName": "KOLKATA",
            "status": 1
        },
        {
            "circleId": 23,
            "circleName": "MUMBAI",
            "status": 1
        },
        {
            "circleId": 25,
            "circleName": "BIHAR AND JHARKHAND",
            "status": 1
        }
    ]
}on
```


{% endtab %}
{% endtabs %}
