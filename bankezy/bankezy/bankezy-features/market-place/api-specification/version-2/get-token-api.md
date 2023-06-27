---
description: >-
  For any given user, this API will generate the user token and share it back
  with partner app. This token needs to be passed to the BankEzy SDK for any
  future communication.
---

# Get Token API



{% swagger method="get" path="" baseUrl="/token-service/client/server/new/v2/token" summary="" %}
{% swagger-description %}
This Api is used to get the token from BankEzy server.
{% endswagger-description %}

{% swagger-parameter in="body" name="referenceId " type="String" required="true" %}
Client reference ID for api call. Example value UUID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sdkPublicKey " type="String" required="true" %}
Public key shared by BankEzy SDK to client app
{% endswagger-parameter %}

{% swagger-parameter in="body" name="firstname " type="String" %}
First Name of customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lastName " type="String" %}
Last Name of customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email " type="String" %}
Verified Email Address of customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="isdCode " type="String" %}
isdCode of customer country
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNumber" type="String" %}
Customer Mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data " type="Map<String,String> " %}
Any extra info to be required to pass
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sdkApiKey" type="String" required="true" %}
ApiKey provided by bankEzy to allow requests from sdk (provided during the onboarding)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountNumber" type="Number" required="true" %}
Unique to number to identify customer. Max 19 digits 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dob" type="Number" %}
Date of birth of customer(yyyyMMdd)
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="text/plain " required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{ 

“resCode”: 100, 

“resDesc”: “SUCCESS”, 

“referenceId”: “asdasdasd” 

serverPubKey: “ahjsgdjlhasgLDJHASHGDAHS”, 

“token”: “asdkjhlajSDGLHJAgslkhdfgkhagDFSHagsfdkhgafsDGafjsdhgas”, 

“expireAt”: 1231231231212 

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

##

{% tabs %}
{% tab title="Sample curl request" %}
```
curl --location --request POST 'https://payment1.pcdev.enstage-sas.com/token-service/client/server/new/token' \
--header 'X-API-KEY: MOB-APP-2001' \
--header 'Content-Type: text/plain' \
--data-raw '{
    "firstName": "firstName",
    dhskhkdhskhkds
    jdskjlkds
    "sdkApiKey": "api-key",
    "lastName": "lastName",
    "accountNumber":1000,
    "isdCode":91,
    "mobileNumber":9999999999,
    "email":"mail@test.com",
    "data":{"custom_attribute1":"custom data"},
    "dob":15051988,
    "referenceId":"askjdhakjdhak"
}'
```
{% endtab %}

{% tab title="Token request sample" %}
Request body will contain the encrypted value of JSON String. Refer [Encryption](../../../api-reference-guide.md#payload-encryption) section.

```
{ 
referenceId: “ASHAGSJHGASGAH”, 
“sdkPublicKey”: “asdbajsdkajvskdghakshgdfakjsgdasfjdgafkhsdfajhgsdfajshgdasdhga”, 
“sdkApiKey”: “ABCDEFGH”, 
“name”: “David beckham”, 
“email”: “OperationalSupport@wibmo.com” 
“accountNumber”: 123123123, 
“isdCode”: 91, 
“mobileNumber”: 9642308308, 
“dob”: 19910807 
“data”: 
{ 
“key1”: “value1”, 
“key2”: “value2” 
. 
. 
. 
“keyn”: “valuen” 
} 
} 
```
{% endtab %}

{% tab title="Token response sample" %}
Response is a string value which is encrypted version of JSON, once client decrypt the value will be output as follows.&#x20;

```json
{ 
“resCode”: "TOK200", 
“resDesc”: “SUCCESS”, 
“referenceId”: “asdasdasd” 
serverPubKey: “ahjsgdjlhasgLDJHASHGDAHS”, 
“token”: “asdkjhlajSDGLHJAgslkhdfgkhagDFSHagsfdkhgafsDGafjsdhgas”, 
“expireAt”: 1231231231212 
} 
```
{% endtab %}
{% endtabs %}

