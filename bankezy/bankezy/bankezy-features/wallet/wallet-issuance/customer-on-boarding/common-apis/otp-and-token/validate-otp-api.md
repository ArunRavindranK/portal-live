---
description: This API helps to validate OTP which is entered by the user
---

# Validate OTP API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/otp/validateOTP/v1 " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The response got from the 

[Get Token API](../get-app-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" %}
text/plain
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="false" %}
Device id of the device used by the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" required="false" %}
The mobile number of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpEventType" required="true" %}
ENROLL
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpRef" required="true" %}
Response from Generate OTP API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpVal" required="true" %}
OTP value entered by user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" required="true" %}
Api token passed as header
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
      "resCode":0,
      "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..NofzkUM6G-vXt_9N.a3wk4f7Nl9kBN3i5mDYzoewars9eTAhVwJz6gJn6NqFHySAdVAGz1Q3-ctSupCHiHQ3JWC3F0d5Tq5w3jmJ5idfJfryOMKsDnfIjKW5dCyct_heTdLNFsjFOICOFGjV7ns3S3sORQEdDRZLATCQFOp85hLVtWzzFK4FTb9t5bF4zB-jdyKwMVPwQEEaZGbTN1uoCnXmEYBtwf4P1NYkj9mOYSrxGk_GHOIL3LPpYuDvQKSw_z_hlKpLjKFI8su9gkv833PU.Bq8aIaMvInvWbX6QPvqUFQ",
      "expiry":1644902027635,
      "accountNumber":"1477"
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
{% code overflow="wrap" %}
```json
curl --location --request POST '<domain>/onboarding/otp/validateOTP/v1'
\--header 'X-API-TOKEN; token'
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'Content-Type: text/plain'
\--data-raw '{ "deviceId":"anid:7vpswUwL4EiBjHgqVgTYmoadZSjS4Ffb2xJ8lv69Muc=:fe89", "mobile":"7000000002", "otpEventType":"ENROLL", "otpRef":"b43cbdfa-dd44-4bdf-99c2-65a657289501", "otpVal":"507471", "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..2ifpzH2-XJkNfp5t.lSUr2CpIV3if17KO3HUgguz4glB487nQDwFlHmhjoeJiXYq4U27lLrCohE6EPqGABOJ9A48WssWTf6ZRv70j_67P03JZFHMYpsZt4warIkOmEXf7gnVA4ENmJA31MQtMIBv6pr918htrBTFCjA5NkWQoEPt5kQd8-PHbNqLkWiHT9O_FACP6pf5Fa91D18bayhnqZPFK2BRwlA.MRkctwoHEEjbURXXY3Cq_A" }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "deviceId":"anid:7vpswUwL4EiBjHgqVgTYmoadZSjS4Ffb2xJ8lv69Muc=:fe89",
   "mobile":"7000000002",
   "otpEventType":"ENROLL",
   "otpRef":"b43cbdfa-dd44-4bdf-99c2-65a657289501",
   "otpVal":"507471",
   "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..2ifpzH2-XJkNfp5t.lSUr2CpIV3if17KO3HUgguz4glB487nQDwFlHmhjoeJiXYq4U27lLrCohE6EPqGABOJ9A48WssWTf6ZRv70j_67P03JZFHMYpsZt4warIkOmEXf7gnVA4ENmJA31MQtMIBv6pr918htrBTFCjA5NkWQoEPt5kQd8-PHbNqLkWiHT9O_FACP6pf5Fa91D18bayhnqZPFK2BRwlA.MRkctwoHEEjbURXXY3Cq_A"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "resCode":0,
      "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..NofzkUM6G-vXt_9N.a3wk4f7Nl9kBN3i5mDYzoewars9eTAhVwJz6gJn6NqFHySAdVAGz1Q3-ctSupCHiHQ3JWC3F0d5Tq5w3jmJ5idfJfryOMKsDnfIjKW5dCyct_heTdLNFsjFOICOFGjV7ns3S3sORQEdDRZLATCQFOp85hLVtWzzFK4FTb9t5bF4zB-jdyKwMVPwQEEaZGbTN1uoCnXmEYBtwf4P1NYkj9mOYSrxGk_GHOIL3LPpYuDvQKSw_z_hlKpLjKFI8su9gkv833PU.Bq8aIaMvInvWbX6QPvqUFQ",
      "expiry":1644902027635,
      "accountNumber":"1477"
   }
}
```
{% endtab %}
{% endtabs %}
