---
description: >-
  This API is used to retrieve coins, gems, wallet balance and investment
  details for the user
---

# Fetch Profile Details API



{% swagger method="get" path="" baseUrl="<domain>/onboarding/userProfile/fetchPortfolioDetails/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login AP](login-api.md)

I
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
        "coinsEarned": 10,
        "gemsEarned": 20,
        "walletBalance": 595673,
        "investmentDetails": null
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

{% tabs %}
{% tab title="Sample Curl Request" %}
```json
curl --location --request GET 'https://payment1.pcdev.enstage-sas.com/onboarding/userProfile/fetchUserProfileDetails/v1'
\--header 'Content-Type: text/plain'
\--header 'X-API-TOKEN:replace_with_basic_auth_to_be_built_by_client'
\--header 'X-API-KEY:MOB-APP-2001'
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "coinsEarned": 10,
        "gemsEarned": 20,
        "walletBalance": 595673,
        "investmentDetails": null
    }
}
```
{% endtab %}
{% endtabs %}
