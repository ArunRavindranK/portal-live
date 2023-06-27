---
description: By calling this API, user can logout from bankezy application.
---

# Logout API



{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/logout/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](login-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="signOutMode" %}
signOutMode 1 - Pin based mode signOutMode 2 - Device based mode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Device unique id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" required="true" %}
The response got from the 

[Get Token API](../../../../../../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS"
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

| Response field | Field description    | Data type |
| -------------- | -------------------- | --------- |
| resCode        | response code        | Integer   |
| resDesc        | response description | String    |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:10000/onboarding/user/logout/v1' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ZJitdRZXJMeJkxFz.PuV48dCHwNI8gt0u1p7wVo8MiLNgyC5BfCkz7Qvpn2NNzXHEgVsfhd4AAHyCq0-FpMHBd5_kR2yZw-fZ-ZQHIqgT-PUOy4H9w1OBDuw0jWfcRtPnT8BNV1bDO7OvVKBplVksyifTLIYX5zFu4HfmHXygEBvv11sL8WUVHyTH8QgLMHLu2qT7l0UBTGHD8pgcZeZAQFdEXPpkglbRVdOedUda7Am1-NSvPLch5s1vyxRNrlR--8xzlfE5munVeYp8ln6L1A.foUnrZNCjNqEcoA_6u9SOw'
\--header 'Content-Type: text/plain'
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Cookie: JSESSIONID=C0D114845B4EC3A92A840A1B862E96F4'
\--data-raw '{
    "signOutMode":1,
    "deviceId":"tdid:zoqDZXDF59W+5yuhCodFoDGCGXTo8uHJkVRhLTOxk6o=:7971",
    "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..b6UC68wkKw3icLR-.8xVJwyqcg-gbagibGl30a-6bcScmGJTYAJbnKt1uqA8n7EYgBYESRB9VDQrqX8p2jJkNidI12XyRf5X033UtyVZ7pWqxN7pdud6ZVf0ZAuh_hTL2Jk7kham1qDM11l2gtRhn0IA34h6NMYMvKZG0Aju0NkIwzcQApY82T689SoYlAIPWJRk3JoLBX0H_LzP_1FvFgKCtebXitQu_3LibG-1orKvhTWTddRARk4dAJSV0xYoF_t6cQ8xMWszyEIhblXV5JQ.aT0zUbt6al4aymQydmLQSQ"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "signOutMode":1,
    "deviceId":"tdid:zoqDZXDF59W+5yuhCodFoDGCGXTo8uHJkVRhLTOxk6o=:7971",
    "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..b6UC68wkKw3icLR-.8xVJwyqcg-gbagibGl30a-6bcScmGJTYAJbnKt1uqA8n7EYgBYESRB9VDQrqX8p2jJkNidI12XyRf5X033UtyVZ7pWqxN7pdud6ZVf0ZAuh_hTL2Jk7kham1qDM11l2gtRhn0IA34h6NMYMvKZG0Aju0NkIwzcQApY82T689SoYlAIPWJRk3JoLBX0H_LzP_1FvFgKCtebXitQu_3LibG-1orKvhTWTddRARk4dAJSV0xYoF_t6cQ8xMWszyEIhblXV5JQ.aT0zUbt6al4aymQydmLQSQ"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS"
}
```
{% endtab %}
{% endtabs %}
