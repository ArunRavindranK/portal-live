---
description: >-
  API to check whether the sim and device binding is completed at the backend
  server
---

# Check status API



{% swagger method="get" path="" baseUrl="<domain>/onboarding/user/auth/v2/checkStatus" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-KEYREF-VAL" required="true" %}
Key reference value received from backend while calling 

[save encrypyted payload api](../../../../version-1/customer-on-boarding/api-specification/sim-and-device-binding/save-encrypted-payload-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Response Details

| Response field | Field description           | Data type |
| -------------- | --------------------------- | --------- |
| response       | SUCCESS or FAILURE response | String    |

#### Response Code

| Code   | Description |
| ------ | ----------- |
| ONB030 | Failure     |
| ONB200 | Success     |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request GET 'domain/onboarding/user/auth/v2/checkStatus' \
\--header 'X-KEYREF-VAL: 202205aLEdeXaEYC'
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'X-API-TOKEN: token' 
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "ONB200",
    "resDesc": "SUCCESS",
    "data": {
        "response": "SUCCESS"
    }
}
```
{% endtab %}
{% endtabs %}
