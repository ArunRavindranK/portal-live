---
description: Fetch auto subscription status
---

# Auto Subscription Status API

{% swagger method="post" path="" baseUrl="<domain>/wallet/autoTopup/subscriptionStatus/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" required="true" name="X-API-TOKEN" type="String" %}
​The token got from the

[login API](https://teams.microsoft.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/\~/changes/1N4jHPuBZcVMjqkduW8F/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/customer-on-boarding/api-reference/authentication-and-authorization/login-api)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" type="String" required="true" %}
Country Code
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="204: No Content" description="" %}
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

{% swagger-response status="403: Forbidden" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Custom response code

| Code | Description                     |
| ---- | ------------------------------- |
| 26   | ​Customer id is empty           |
| 100  | FAILURE                         |
| 102  | Country code should not be zero |
| 150  | Status is inactive              |

{% tabs %}
{% tab title="Sample curl command" %}
{% code overflow="wrap" %}
```json
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/wallet/autoTopup/subscriptionStatus/v1'
\--header 'Content-Type: application/json'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'X-API-TOKEN:replace_with_basic_auth_to_be_built_by_client' --data-raw'{ "countryCode": +91'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "countryCode": +91
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": 200,
  "resDesc": "autotopup status fetched successfully",
  "data": {
    "status": "A",
    "thresholdAmt": 100000,
    "topupAmt": 110000,
    "remarks": "SUCCESS",
    "subscriptionInfo": {
      "autoPayDesc": "Bill is paid 5th of every month",
      "cardAliasName": null,
      "cardMaskedNumber": "**** **** **** 6226",
      "cardRefId": "16",
      "merchantName": "Load Money. Merchant",
      "nameOnCard": "HDFC Card",
      "nickName": null,
      "subscriberName": "Load Money. Merchant",
      "recurringPaymentRefId": 2021060210010010400,
      "merchantId": "171756421435003980",
      "subscriberId": "171756421435003980"
    }
  }
}
```
{% endtab %}
{% endtabs %}
