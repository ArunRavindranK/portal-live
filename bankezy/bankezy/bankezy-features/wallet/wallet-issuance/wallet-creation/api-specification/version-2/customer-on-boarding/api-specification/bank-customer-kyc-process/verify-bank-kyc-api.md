---
description: API to verify the KYC details of the customer with bank's system.
---

# Verify Bank KYC API



{% swagger method="post" path="" baseUrl="<domain>/onboarding/kyc/v2/verifyBankKyc " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)

 or 

[Get Token API](../../../../version-1/customer-on-boarding/common-apis/get-app-token-api.md)

​
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" %}
text/plain
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankCustId" required="true" %}
The unique bank customer id of the customer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":{
      "code":"2000",
      "message":"Verified",
      "displayMessage":"Bank KYC successfully completed",
      "kycLevel":150
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

| Response Field | Field Description         | Data Type |
| -------------- | ------------------------- | --------- |
| code           | response Code             | String    |
| message        | response message          | String    |
| displayMessage | detailed response message | String    |
| kycLevel       | kyc level                 | Integer   |

#### Response Code

| Response Code | Response Description                                             |
| ------------- | ---------------------------------------------------------------- |
| ONB045        | Bank customer id is mandatory.                                   |
| ONB046        | Bank Id is mandatory.                                            |
| ONB047        | Bank Kyc is already verified.                                    |
| ONB006        | Entered Bank Customer id is already existing                     |
| ONB048        | Request could not be processed at this time, Please retry again. |
| ONB004        | Success                                                          |



{% tabs %}
{% tab title="Sample Curl Request" %}
{% code overflow="wrap" %}
```
curl --location --request POST '<domain>/onboarding/kyc/v2/verifyBankKyc'
\--header 'X-API-TOKEN: token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain' --data-raw '{ "bankCustId":"11224343434" }'

```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "bankCustId":"11224343434"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":"ONB200",
   "resDesc":"SUCCESS",
   "data":{
      "code":"2000",
      "message":"Verified",
      "displayMessage":"Bank KYC successfully completed",
      "kycLevel":150
   }
}
```
{% endtab %}
{% endtabs %}
