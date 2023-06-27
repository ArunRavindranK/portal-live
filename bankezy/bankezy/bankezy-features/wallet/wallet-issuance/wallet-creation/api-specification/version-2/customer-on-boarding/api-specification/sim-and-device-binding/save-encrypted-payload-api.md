---
description: >-
  This API helps to save the payload which is encrypted by using public key
  shared by server
---

# Save Encrypted Payload API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/auth/v2/saveEncryptedPayLoad" summary="For doing encryption/decryption RSA/ECB/OAEPPADDING algorithm used." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="payLoad" required="true" %}
encrypted payload by using 

[public key](broken-reference)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "keyForPayload": "202205aLEdeXaEYC",
        "destinationNo": "1234567890",
        "envKeyword": "DEV",
        "programId": 1111
    }
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

| Response Field | Field description                                    | Data type |
| -------------- | ---------------------------------------------------- | --------- |
| keyForPayload  | newly generated key ref for retrieving saved payload | String    |
| destinationNo  | mobile no of the operator                            | String    |
| envKeyWord     | different environmental key                          | String    |
| programId      | 4 digit program id                                   | Integer   |

#### Response Code

| Code   | Description |
| ------ | ----------- |
| ONB030 | Failure     |
| ONB200 | Success     |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/user/auth/saveEncryptedPayLoad/v1' \
--header 'X-API-TOKEN: token' \
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Content-Type:text/plain'
--data-raw '{
    "payLoad":"Q9/SfT5crLfrUrgERqlk5FFUHI3SKv8t0AoHTAWxxk8kp5A0VdNMZkOl/WbpI7/K982DU5EsnlyONJ/F8+kpNnZ9kBJ/TizvXsnyL2XShyagRK3tvErAVVjdM0hkuEN9vclx3vEJSvnjUNsgTqFVrn29YJDbrfipNd1syr8vZbY="
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json5
{
    "payLoad":"Q9/SfT5crLfrUrgERqlk5FFUHI3SKv8t0AoHTAWxxk8kp5A0VdNMZkOl/WbpI7/K982DU5EsnlyONJ/F8+kpNnZ9kBJ/TizvXsnyL2XShyagRK3tvErAVVjdM0hkuEN9vclx3vEJSvnjUNsgTqFVrn29YJDbrfipNd1syr8vZbY="
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "ONB200",
    "resDesc": "SUCCESS",
    "data": {
        "keyForPayload": "202205aLEdeXaEYC",
        "destinationNo": "1234567890",
        "envKeyword": "DEV",
        "programId": 1111
    }
}
```
{% endtab %}
{% endtabs %}
