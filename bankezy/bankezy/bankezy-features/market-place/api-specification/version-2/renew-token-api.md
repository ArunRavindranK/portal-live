---
description: >-
  This Api is used to renew the expired token, while renewing ,the BankEzy
  server will check if session is terminated by Client server or not.
---

# Renew Token Api



{% swagger method="post" path="" baseUrl="/token-service/client/app/renew/v2/token" summary="This API is used to renew the token generated" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
\<token-passed-from-client-server>
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}
Customer account number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" required="true" %}
OAuth token in the body
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
Response Body (after decryption) 

{ 

“resCode”: 100, 

“resDesc”: “SUCCESS”, 

“referenceId”: “asdasdasd” 

“token”: “asdkjhlajSDGLHJAgslkhdfgkhagDFSHagsfdkhgafsDGafjsdhgas”, 

“expireAt”: 1231231231212, 

} 
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Invalid Token Passed" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Sample curl request" %}
```
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/token-service/client/app/renew/token' \
--header 'X-API-TOKEN: replace_with_token _from_new_token_api_response'\
--header 'X-ACCOUNT-NUMBER: provide the user account number' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'Content-Type: text/plain'
--data-raw '{
    "token":"erewfsdfsdfdsf"
}'
```
{% endtab %}

{% tab title="Token request sample" %}
```
{
  "token":"erewfsdfsdfdsf"
}
```
{% endtab %}

{% tab title="Token response sample" %}
```
{
  "resCode":"TOK200",
  "resDesc":"SUCCESS",
  "data":{
           "loginId":3441691,
           "accountNumber":"156",
           "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..ItxOcktFfgzD5ynD.hmCVyC5JCbxtUh10kh9KOFHwm61L9cr3BhyQUiq-tFPMQpMQ_JMKD83dU0UDX6cblfBMoVLAoVEEOjkWpt7ehLSGrfkoVLAPajtlLEmduq0okIDV4OCio2IX35ApvgR_Cl_XiDB4FX6UcQTqo_xg5ANBu3nrflvDPKug2f7JdnHeqIhSDaC2PjZ56WzyQCW--tiXgOQtJxumEXYke-peLn8ME6mSbeSxepQv0PYuijJ8RqQZSOb7zbttW1e32xac72U2YDiq.9K0azrOkBwn6YChoy92eiA",
           "expiryDate":1644822181108
           }
  }

```
{% endtab %}
{% endtabs %}

