---
description: >-
  This API is called in case of a system time-out or in scenarios where client
  did not receive any response for an API
---

# Check Status API

Using Client Txn ID, this API can fetch the details of the response dump of any API (Transactional/Non-Transactional) if available.

{% swagger method="post" path="" baseUrl="api/v1/checkStatus" summary="" %}
{% swagger-description %}
Request body will contain the encrypted token. Encryption will be done by the client using the client key provided by Wibmo Team. Encryption/ Decryption methodology - AES 192 CBC.

Note - Below are the request parameters in clear text that needs to be encrypted by the client. The below parameters should not be shared in clear text.
{% endswagger-description %}

{% swagger-parameter in="body" name="token" type="String" required="true" %}
Request body will contain the encrypted token. Encryption will be done by the client using the client key provided by Wibmo Team. Encryption/ Decryption methodology - AES-192-CBC

Note - Below are the request parameters in clear text that need to be encrypted by the client. The below parameters should not be shared in clear text.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-api-key" required="true" type="String" %}
Special token that the client needs to provide when making API calls. Will be shared along with access to Prepaid Platform Sandbox environment | Ex. -ABCDEF12345
{% endswagger-parameter %}

{% swagger-parameter in="body" name="messageCode" type="Numeric(4)" required="true" %}
API Code to uniquely identity ‘Check Status’ API | Ex.

`2050`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="verifyclientTxnId" type="String (100)" required="true" %}
Unique Id generated by the client for each API request. | Ex.

`923eh42r3jbd4335r3et53`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requestDateTime " type="Numeric(14)" required="true" %}
Local Date and time stamp in YYYYMMDDHHMMSS with time in 24-hour format | Ex:

`20161031000000`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="clientId" type="String(15)" required="true" %}
Uniquely identifies the Client. During program enrollment each Client is provided with a unique client id by Prepaid Aero. | Ex.

`FintechA`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankId " type="Numeric(4)" required="true" %}
Uniquely identify the card issuer. Bank Id is provided by Prepaid Platform during program enrollment to uniquely identify the card issuer | Ex.

`1234`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fromDate" type="String(10)" required="false" %}
Date range provided by the client to search for a particular clientTxnId in a given date range in DD/MM/YYYY format | Ex:

`07/08/2022`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="secureCode" type="String(25)" required="true" %}
Unique static parameter to uniquely identifies the client on payload level for performing operations. | Ex.

`ABCD12345`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="toDate" type="String(10)" required="false" %}
Date range provided by the client to search for a particular clientTxnId in a given date range in DD/MM/YYYY format | Ex:

`08/08/2022`
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    //Response
}
```
{% endswagger-response %}
{% endswagger %}

#### Response Body

| **urn**                 | numeric(10) | Mandatory | A unique reference number for the generated card.                  | Unique identifier for card/wallet                              | 1000058915                |
| ----------------------- | ----------- | --------- | ------------------------------------------------------------------ | -------------------------------------------------------------- | ------------------------- |
| **responseCode**        | string(4)   | Y         | Response code of the action executed.                              | Contains the status of the transaction. 00 indicates success.  | 00                        |
| **messageCode**         | numeric(4)  | Y         | Code to Identify check status response type.                       | Refer to the message code reference.                           | 2051                      |
| **clientTxnId**         | string(100) | Y         | Unique Id generated by the client for each transaction.            | Value copied from the request                                  | 20150701235959xhstiesqfds |
| **bankId**              | numeric(4)  | Mandatory | Uniquely identify the card issuer                                  | Bank Id is provided by Prepaid System during program enrolment | 1234                      |
| **accosaTransactionId** | numeric(10) | Y         | Unique id for a particular transaction generated in Prepaid system | Unique Identifier for a transaction                            | 3591893                   |
| **responseDump**        | String(100) | Mandatory | Response Dump based on client txn id will be sent                  | If available, response dump of any API will be sent            | “The whole response Dump” |

{% tabs %}
{% tab title="Curl" %}
```json
Sample Check Status API Request
https://pp-sandbox.wibmo.com/api/v1/checkStatus
Sample Request
Encrypted req->
{
"token":"Pl8F5kDZcvADIiursiAvvbHNuL9Wv5eaFdorGVFU6FKfIEnV/YskkzJlAov2ZHJWnqGNLOXfBq4SQqw8Ep4sK0gCAAkRXATCb1nSY6s=" 
}
// Sample token. Client will have to generate this token. 
Decrypted req->
{ 
   "messageCode": "2050",
   "clientId": "WibmoClient",
   "requestDateTime": "20221116010353",
   "secureCode": "AfZtpO5krtySIhXyNmGg1G",
   "verifyclientTxnId": "Acti_V3_dSUSxzDW8s",
   "fromDate": "2022-10-20",
   "toDate": "2022-11-20",
   "bankId": "2010"
}
```
{% endtab %}

{% tab title="Response (Success)" %}
<pre class="language-json"><code class="lang-json">Encrypted Response->
<strong>{
</strong>"token":"Pl8F5kDZcvADIiursiAvvbHNuL9Wv5eaFdorGVFU6FKfIEnV/YskkzJlAov2ZHJWnqGNLOXfBq4SQqw8Ep4sK0gCAAkRXATCb1nSY6s=" 
}
//Sample token. Client will have to decrypt the token shared in the response body
Decrypted Response->
{
    "bankId": 2010,
    "clientTxnId": "Acti_V3_dSUSxzDW8s",
    "accosaTransactionId": 0,
    "response_dump": [
        "{\"urn\":408,\"customerId\":\"custid_V3_xPL4SdIlUd\",\"description\":\"Card Creation\",\"responseCode\":\"201\",\"messageCode\":1011,\"clientTxnId\":\"Acti_V3_dSUSxzDW8s\",\"clientId\":\"WibmoClient\",\"responseDateTime\":\"20221116123640\",\"accosaTransactionId\":7486,\"responseMessage\":\"CARD_CREATED_SUCCESSFULLY\",\"bankId\":2010,\"accosaRefNo\":\"783\",\"cardNumber\":\"p7+aKDkl\/CnPZq2hlfTPHenjqAp4EQj5wsPBgJxa1G0=\",\"cardProfileId\":150,\"loadAmount\":100000,\"availableBalance\":100000,\"availableCashLimit\":0,\"loginProfId\":0}"
    ],
    "messageCode": 2051,
    "responseCode": "00"
}
</code></pre>
{% endtab %}

{% tab title="Response (Failure)" %}
<pre class="language-json"><code class="lang-json">Encrypted Response->
<strong>{
</strong>"token":"Pl8F5kDZcvADIiursiAvvbHNuL9Wv5eaFdorGVFU6FKfIEnV/YskkzJlAov2ZHJWnqGNLOXfBq4SQqw8Ep4sK0gCAAkRXATCb1nSY6s=" 
}
//Sample token. Client will have to decrypt the token shared in the response body
Decrypted Response->
{
    "bankId": 2010,
    "responseDump": "NO API RESPONSE DUMP AVAILABLE FOR THE CLIENT TXN ID",
    "accosaTransactionId": 0,
    "messageCode": 0,
    "responseCode": "01"
}
</code></pre>
{% endtab %}
{% endtabs %}

| 00 | SUCCESS |
| -- | ------- |
| 01 | FAILURE |