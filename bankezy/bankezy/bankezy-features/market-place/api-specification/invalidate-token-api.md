# Invalidate Token Api

This Api is used to invalidate the token, to be used in logout / session timeout scenarios.

{% swagger method="post" path="" baseUrl="/token-service/client/server/invalidate/token" summary="This API will invalidate the token." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="tokenReferenceId" type="String" required="true" %}
Token referenceId used to invalidate the session. This can be found in the get Token api response
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
Value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
Response Body (after decryption): 

{ 

“resCode”: 100, 

“resDesc”: “SUCCESS”, 

“referenceId”: “asdasdasd” 

“token”: “asdkjhlajSDGLHJAgslkhdfgkhagDFSHagsfdkhgafsDGafjsdhgas”, 

“expireAt”: 1231231231212, 

} 
```

**Request example**

```
Request body will contain the encrypted value of JSON String
```

```
 

{ 

“tokenReferenceId”:”sdjfsjdgfljhasgdflhjasgdfjhasd” 

} 
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Invalid Token Passe" %}
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
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/token-service/client/server/invalidate/token' \
--header 'Content-Type: text/plain' \
--header 'X-API-KEY: MOB-APP-2001' \
--data-raw '{
    "tokenReferenceId": "replace_with_referenceid_from_new_token_api_response"
}'
```
{% endtab %}

{% tab title="Token request sample" %}
```
{
    "tokenReferenceId": "replace_with_referenceid_from_new_token_api_response"
}
```
{% endtab %}

{% tab title="Token response sample" %}
```
{
  "resCode":200,
  "resDesc":"SUCCESS",
  "data":{
           "resCode":100,
           "resDesc":"Success"
           }
  }
```
{% endtab %}
{% endtabs %}
