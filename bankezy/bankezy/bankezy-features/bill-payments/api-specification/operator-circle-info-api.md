---
description: To Fetch operator and circle for customer mobile number
---

# Operator Circle Info API

{% swagger method="post" path="" baseUrl="<domain>retail-service/operators/circles/details/v1" summary="To Fetch operator and circle for customer mobile number" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
will be shared upon onboarding api consumers (clients)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[Get Token API](../../market-place/api-specification/get-token-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile Number" type="String" required="true" %}
Customer Mobile Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="service_id" type="int" required="false" %}
To specify type of category
{% endswagger-parameter %}

{% swagger-parameter in="header" name="CONTENT-TYPE" required="false" %}
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

#### Response Details

| Response Body | Data Type | Field Description                                          |
| ------------- | --------- | ---------------------------------------------------------- |
| resCode       | int       | 200- Success                                               |
| resDesc       | String    | Response Description                                       |
| circleRefID   | int       | Id indicating the region of the operator                   |
| circleName    | String    | Name of the circle                                         |
| circleCode    | String    | Short of the circle                                        |
| operatorCode  | String    | Short code of the operator                                 |
| operatorName  | String    | Name of the operator                                       |
| fixedBill     | boolean   | Represents whether the Mobile Number has fixed bill or not |
| prefixNumber  | int       | Prefix number of mobile number                             |

{% tabs %}
{% tab title="sample curl  Request" %}
```json
curl --location --request POST 'https://app9.pcdev.enstage-sas.com/retail-service/operators/circles/details/v1' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'Content-Type: text/plain' \
--data-raw '{
  "mobileNumber": "9848391094",
  "serviceId": 0
}'
```
{% endtab %}

{% tab title="Request Example" %}
```json
{
  "mobileNumber": "9848391094",
  "serviceId": 0
}
```
{% endtab %}

{% tab title="Response Example" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "circleRefID": 2,
        "circleName": "Andhra Pradesh Telangana",
        "circleCode": "AP",
        "operatorCode": "IDEA",
        "operatorName": "IC",
        "fixedBill": "False",
        "prefixNumber": ""
    }
}
```
{% endtab %}
{% endtabs %}
