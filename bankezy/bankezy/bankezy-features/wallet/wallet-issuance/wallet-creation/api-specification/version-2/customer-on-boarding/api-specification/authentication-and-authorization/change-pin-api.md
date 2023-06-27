---
description: >-
  After Login, User can change pin by using the settings option in the
  application
---

# Change PIN API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/v2/changePin" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="newPin" required="true" %}
New pin entered by the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currentPin" required="true" %}
Existing pin
{% endswagger-parameter %}

{% swagger-parameter in="body" name="signInMode" required="true" %}
SignInMode should be 1 since it is change pin
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "msg": "Pin has been reset successfully"
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

| Response field | Field description | Data type |
| -------------- | ----------------- | --------- |
| msg            | response message  | String    |

#### Response Code

| Code   | Description                                                     |
| ------ | --------------------------------------------------------------- |
| ONB014 | Sign in mode mandatory                                          |
| ONB015 | Invalid Sign In Mode                                            |
| ONB016 | PIN mandatory                                                   |
| ONB049 | Invalid Pin                                                     |
| ONB050 | PIN length mis match                                            |
| ONB052 | Invalid New Pin                                                 |
| ONB004 | Request could not be processed at this time, Please retry again |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:10000/onboarding/user/changePin/v1' \
\--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
\--header 'Cookie: JSESSIONID=C0D114845B4EC3A92A840A1B862E96F4'
\--data-raw '{
    "newPin":"2222",
    "currentPin":"1111",
    "signInMode":1
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json5
{
    "newPin":"2222",
    "currentPin":"1111",
    "signInMode":1
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "ONB200",
    "resDesc": "SUCCESS",
    "data": {
        "msg": "Pin has been reset successfully"
    }
}
```
{% endtab %}
{% endtabs %}
