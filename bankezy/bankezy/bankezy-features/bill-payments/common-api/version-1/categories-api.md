# Categories API

{% swagger method="get" path="" baseUrl="<domain>retail-service/home/v1/categories" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The response got from the 

[Get Token API](../../../wallet/wallet-issuance/wallet-creation/api-specification/version-1/customer-on-boarding/common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
will be shared upon onboarding api consumers (clients)
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

## Response Details

| Response Body     | Data Type | Field Description                                                  |
| ----------------- | --------- | ------------------------------------------------------------------ |
| statusCode        | int       | Success & Failure Status Codes                                     |
| statusDesc        | String    | Response Description                                               |
| categoryId        | int       | Unique identifier for the category                                 |
| categoryName      | String    | Unique name for category                                           |
| serviceProviderId | int       | Unique identifier to identify the service provider to connect with |
| status            | int       | Indicates whether the category is active are not                   |

{% tabs %}
{% tab title="Sample Curl Command" %}
```json
curl --location --request GET 'https://app9.pcdev.enstage-sas.com/retail-service/home/v1/categories' \
--header 'X-API-KEY:MOB-APP-2001' \​
--header 'X-API-TOKEN:eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \​
```
{% endtab %}

{% tab title="Response Example" %}


```json
{
  "statusCode": 200,
  "statusDesc": "Success",
  "data": [
    {
      "categoryId": 1,
      "categoryName": "DTH",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 2,
      "categoryName": "LOAN",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 3,
      "categoryName": "RETAIL",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 4,
      "categoryName": "INSURANCE",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 5,
      "categoryName": "GAS",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 6,
      "categoryName": "CABLE",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 7,
      "categoryName": "MOBILE POSTPAID",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 8,
      "categoryName": "BROADBAND POSTPAID",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 9,
      "categoryName": "EDUCATIONAL FEES",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 10,
      "categoryName": "LPG GAS",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 11,
      "categoryName": "LANDLINE POSTPAID",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 12,
      "categoryName": "WATER",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 13,
      "categoryName": "MOBILE PREPAID",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 14,
      "categoryName": "FASTAG",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 15,
      "categoryName": "ENTERTAINMENT",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 16,
      "categoryName": "ELECTRICITY",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 17,
      "categoryName": "EDUCATION",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 18,
      "categoryName": "TRAVEL-SUB",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 19,
      "categoryName": "HOUSING SOCIETY",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 20,
      "categoryName": "SUBSCRIPTION",
      "status": 1,
      "serviceProviderId": 105
    },
    {
      "categoryId": 21,
      "categoryName": "HOSPITAL",
      "status": 1,
      "serviceProviderId": 105
    }
  ]
}
```
{% endtab %}
{% endtabs %}
