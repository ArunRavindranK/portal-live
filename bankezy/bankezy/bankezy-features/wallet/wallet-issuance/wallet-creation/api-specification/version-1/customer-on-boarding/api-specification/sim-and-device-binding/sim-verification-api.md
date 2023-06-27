# Sim verification API

This API will be called while user login. If Sim Verification feature is enabled, App will call this API to enable one tap payment(ITP).&#x20;

For this purpose system will check if hashed device unique id is matching with the saved details. If matches system will return ITP true and put the same in user session.

{% swagger method="get" path="" baseUrl="<domain>/onboarding/user/auth/simVerification/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-DEVICE-UNIQUEID" required="true" %}
Hashed and encrypted device unique Id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../authentication-and-authorization/login-api.md)

 or 

[Get Token A](../../../../../../../../market-place/api-specification/version-1/get-token-api.md)


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

| Response field | Field description                                       | Data type |
| -------------- | ------------------------------------------------------- | --------- |
| token          | updated token with itp enabled/disabled based on status | String    |
| expiry         | new expiry of the token                                 | Long      |
| itpEnabled     | if sim and device binding enabled this will be true     | Boolean   |

{% tabs %}
{% tab title="Sample curl request" %}
{% code overflow="wrap" %}
```json
curl --location --request GET 'http://localhost:8083/onboarding/user/auth/simVerification/v1' \
\--header 'X-DEVICE-UNIQUEID: dpZTeBcWEUvTHdnfy4NuwDlbViGzdv1Gvg5BEBwM4wuGnGjmNUcS4p7pEMJhogLzWHss1wZIO8HO4R8yD/d4uvhHFIqbmF05JjXCErFzYtyevAqGGSII2IIVMafEAgfu5AggIRbyFsvQZVwRTRXB8U3x8jiAfq7h6FfzJycc9tw=' \
\--header 'X-API-TOKEN: TOKEN'
\--header 'X-API-KEY:MOB-APP-2001'
```
{% endcode %}
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "token": "eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..jPOTgR1pQjghgoSg.4EQaxMA1nWFRdyM7ziUua6JOxM-4qSU_rs6YXss_cwDwWTAkcpCqi-4zB63qNzLhq7y6RyFeGPM0FWVBCNPa2EIbyAS0qntQa_5vBUU0x8G2W1pj9c8M7R0uPSFF0PTUOKj6XqsPyXbxKwz1DOXg_HHBcsGsJ9oeLXX8nO4XslC6vXEA9iKe8KqDfzgJoNEJA8jFyoCLe2xbt657fpXMcaslJlyFRgmJs00BvjyBke4ABFVhIOuwWUQjinfeu4JeLSiu3dde4I24fJr9dxyDft80kw.g_DZFcwRrk_Z9eZl0c27PQ",
        "expiry": 1651815120745,
        "itpEnabled": false
    }
}
```
{% endtab %}
{% endtabs %}
