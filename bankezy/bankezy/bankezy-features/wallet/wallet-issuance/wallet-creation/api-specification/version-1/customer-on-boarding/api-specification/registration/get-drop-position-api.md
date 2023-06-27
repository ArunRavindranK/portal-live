---
description: Provides view on the User Journey if dropped in between the Registration flow
---

# Get Drop Position API



{% swagger method="get" path="" baseUrl="<domain>/onboarding/userDropout/getDropPosition/v1 " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the  

[Get Token API](../../common-apis/get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "actionCode":1,
      "stepBased":false
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

| Response field | Field description                                                                                                                                                  | Data type |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------- |
| actionCode     | Unique id to indicate the next course of action. ActionCode 0 (no drop out) 1(device permission screen) 2 (UPI registration screen) 3 (Kyc screen) 4 (credentials) | Integer   |
| stepBased      | Flag to indicate id the feature is enabled or not                                                                                                                  | Boolean   |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request GET 'http://localhost:8083/onboarding/userDropout/getDropPosition/v1 ' \
\--header 'X-API-TOKEN: TOKEN'
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Cookie: JSESSIONID=0DC4D4A485D31EA50BEA0795064A833B'
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "actionCode":1, //Unique ID to indicate the next course of action 
                        for the user to do if the feature is enabled
      "stepBased":false //Flag to indicate if this feature is enabled or not
   }
}
```
{% endtab %}
{% endtabs %}
