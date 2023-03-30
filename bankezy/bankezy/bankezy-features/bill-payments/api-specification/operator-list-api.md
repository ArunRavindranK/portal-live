---
description: To fetch list of operators based on category
---

# Operator List API

{% swagger method="post" path="" baseUrl="<domain>retail-service/operators/List/v1" summary="To fetch list of operators based on category" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[Get Token A](../../market-place/api-specification/get-token-api.md)

PI
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
will be shared upon onboarding api consumers (clients)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="CONTENT-TYPE" %}
text/plain
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

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

| Response Body      |         |                                                                     |
| ------------------ | ------- | ------------------------------------------------------------------- |
| statusCode         | int     | Success & Failure status Codes                                      |
| statusDesc         | String  | Response Description                                                |
| operatorPrefix     | String  | Indicates the short name of the operator                            |
| operatorName       | String  | Indicates the name of the operator                                  |
| category           | String  | Name of the category                                                |
| billFetchSupported | Boolean | Indicates whether Bill Fetch option supported or not                |
| bbps               | Boolean | Biller type id BBPS/Non-BPPS                                        |
| adhoc              | Boolean | Indicates whether biller supports   Full payment or Partial payment |

{% tabs %}
{% tab title="sample curl  Request " %}
```json
curl --location --request POST 'https://app9.pcdev.enstage-sas.com/retail-service/operators/List/v1' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'Content-Type: text/plain' \
--data-raw '{
  "serviceId": 1
}'
```


{% endtab %}

{% tab title="Request Example" %}
```json
{
  "serviceId": 1
}
```


{% endtab %}

{% tab title="Response Example" %}
```json
{
    "responseTimeTakenMs": 0,
    "statusCode": 200,
    "statusDesc": "Success",
    "dataList": [
        {
            "operatorPrefix": "AT",
            "operatorName": "AIRTEL",
            "category": "MOBILE PREPAID",
            "billFetchSupported": false,
            "bbps": false,
            "adhoc": false
        },
        {
            "operatorPrefix": "BL",
            "operatorName": "BSNL",
            "category": "MOBILE PREPAID",
            "billFetchSupported": false,
            "bbps": false,
            "adhoc": false
        },
        {
            "operatorPrefix": "IC",
            "operatorName": "IDEA",
            "category": "MOBILE PREPAID",
            "billFetchSupported": false,
            "bbps": false,
            "adhoc": false
        },
        {
            "operatorPrefix": "JR",
            "operatorName": "RELIANCE JIO",
            "category": "MOBILE PREPAID",
            "billFetchSupported": false,
            "bbps": false,
            "adhoc": false
        },
        {
            "operatorPrefix": "MT",
            "operatorName": "MTNL",
            "category": "MOBILE PREPAID",
            "billFetchSupported": false,
            "bbps": false,
            "adhoc": false
        },
        {
            "operatorPrefix": "VF",
            "operatorName": "VODAFONE",
            "category": "MOBILE PREPAID",
            "billFetchSupported": false,
            "bbps": false,
            "adhoc": false
        }
    ]
}
```


{% endtab %}
{% endtabs %}
