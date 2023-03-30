---
description: The API can be used to validate scan url.
---

# Validate scan pay url API



{% swagger method="post" path="upi-integration/upi/transaction/v1/validateUrl" baseUrl="" summary="Post scan to validate sign will use this url." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
TOKEN
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceFingerPrint" required="true" %}
Device fingerprint of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payerVpa" required="true" %}
VPA of the customer to be used for payment
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payeeName" required="true" %}
Name of the payee
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" type="Long" name="amount" %}
Amount for transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="upiRequestId" required="true" %}
Unique id sent to UPI switch for the request
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="bankAccountUniqueId" %}
Unique id for the selected bank account
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="remarks" type="" %}
Any transaction summary
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="currency" %}
Currency code
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
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

{% swagger-response status="404: Not Found" description="" %}
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

## Response Details

| Response Field          | Field Description                                                                                          | Data Type                          | Length                   |
| ----------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------- | ------------------------ |
| status                  | SUCCESS, FAILURE status of the API                                                                         | String                             | Variable, 5–8 characters |
| merchantId              | Unique id for the merchant as passed in request headers                                                    | String                             | Variable, 5–8 characters |
| merchantChannelId       | Unique id for the merchant channel as passed in request headers                                            | String                             | Length: 36 characters    |
| merchantRequestId       | Merchant generated id for the transaction                                                                  | String                             | Length: 36 characters    |
| merchantCustomerId      | Merchant generated unique profile id for customer as passed in the request                                 | String                             | Length: 36 characters    |
| customerMobileNumber    | Customer mobile number                                                                                     | String                             | 12 digits mobile number  |
| payerVpa                | Customer vpa used for the payment                                                                          | String                             | Length: 36 characters    |
| payeeMcc                | MCC for the payee                                                                                          | String                             | Variable, 5–8 characters |
| payeeMerchantCustomerId | Merchant generated unique id for customer who received the payment. Only if it is an onus P2P transaction. | String                             | Length: 36 characters    |
| payeeVpa                | Vpa of the upi user who received the payment                                                               | String                             | Length: 36 characters    |
| refUrl                  | Reference url for the intent transaction                                                                   | String                             | Length: 36 characters    |
| bankAccountUniqueId     | Unique id for the selected bank account                                                                    | As passed in the request           | Length: 36 characters    |
| bankCode                | Bank code of the account which was used                                                                    | Valid bank IIN                     | Length: 36 characters    |
| maskedAccountNumber     | Masked account number of the account which was used                                                        | XXXX123456                         | Length: 36 characters    |
| amount                  | Amount for the payment                                                                                     | long                               | Length: 36 characters    |
| transactionTimestamp    | Timestamp of when the transaction was attempted                                                            | Transaction id returned by gateway | Length: 36 characters    |
| gatewayReferenceId      | Reference id returned by the gateway                                                                       | String                             | Length: 36 characters    |
| gatewayResponseStatus   | Response status returned by gateway                                                                        | String                             | Variable, 5–8 characters |
| udfParameters           |                                                                                                            |                                    | Variable, 5–8 characters |
|                         |                                                                                                            |                                    |                          |
|                         |                                                                                                            |                                    |                          |
|                         |                                                                                                            |                                    |                          |

{% tabs %}
{% tab title="Sample Request" %}
```json
{
    "url": "upi://pay?pa=test@mypsp&pn=3dqc8tkr2kb&tn=SignedIntentTesting&am=&mam=null&cu=INR&tr=UPITestHelper1&mode=00&orgid=158002&sign=MEUCIQDfuE08NavtqTAeOW+WBwDuFBUa83KGipzmyWeOOQZd8wIgFfRY6jwtty0WleXUT2Ir4jnfHpa59K4ZB8SVsd+R6JE=",
    "udfParameters": "{}"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```json
{    
"resCode": 200,    
"errorMessage": "SUCCESS"
}
```
{% endtab %}

{% tab title="Sample Curl Command" %}
```json
curl --location --request POST 'https://bankezy-azure.pcdev.enstage-sas.com/upi-integration/upi/transaction/v1/validateUrl' \
--header 'X-ACCOUNT-NUMBER: 3110' \
--header 'X-PROGRAM-ID: 2001' \
--header 'Content-Type: application/json' \
--data-raw '{
    "url": "upi://pay?pa=test@mypsp&pn=3dqc8tkr2kb&tn=SignedIntentTesting&am=&mam=null&cu=INR&tr=UPITestHelper1&mode=00&orgid=158002&sign=MEUCIQDfuE08NavtqTAeOW+WBwDuFBUa83KGipzmyWeOOQZd8wIgFfRY6jwtty0WleXUT2Ir4jnfHpa59K4ZB8SVsd+R6JE=",
    "udfParameters": "{}"
}'
```
{% endtab %}
{% endtabs %}
