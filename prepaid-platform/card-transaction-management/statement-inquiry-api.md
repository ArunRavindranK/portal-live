---
description: >-
  This API is used to showcase Transaction history on Website/Portal with
  pagination.
---

# Statement Inquiry API

Statement Inquiry API is called by the client to fetch the relevant transactions on a card. Transactions within the specified date range along with the balance of the card is fetched and sent to the client.

{% swagger method="post" path="" baseUrl="api/v1/statementInquiry" summary="" %}
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
API Code to uniquely identity ‘Verify Cardholder’ API | Ex.

`1072`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="clientId" type="String(15)" required="true" %}
Uniquely identifies the Client. During program enrollment each Client is provided with a unique client id by Prepaid Aero. | Ex.

`FintechA`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="secureCode" type="String(25)" required="true" %}
Unique static parameter to uniquely identifies the client on payload level for performing operations. | Ex.

`ABCD12345`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="clientTxnId" type="String (100)" required="true" %}
Unique Id generated by the client for each API request. | Ex.

`20150701235959xhstiesqfds`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requestDateTime " type="Numeric(14)" required="true" %}
Local Date and time stamp in YYYYMMDDHHMMSS with time in 24-hour format | Ex:

`20161031000000`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankId " type="Numeric(4)" required="true" %}
Uniquely identify the card issuer. Bank Id is provided by Prepaid Platform during program enrollment to uniquely identify the card issuer | Ex.

`1234`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="entityId " type="Numeric(4)" required="false" %}
Defaults to parent branch of the client i.e., 100 if not provided. This option is useful if cards need to be created and activated under a specific entity/outlet |

`100`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerId " type="string(20) " required="false" %}
Uniquely identifies the cardholder in the client system | Ex:

`91xxxxxxxx`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fromDate" type="String(10)" required="false" %}
Statement Details from Date in DD/MM/YYYY format | Ex:

`07/08/2022`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="toDate" type="String(10)" required="false" %}
Statement Details from Date in DD/MM/YYYY format | Ex:

`08/08/2022`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="last4digits " type="numeric(4) " required="true" %}
Last 4 digit of the customer card number | Ex:

`3781`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="urn" type="numeric(10)" required="true" %}
A unique reference number for the generated wallet | Ex:

`1000058915`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageNumber" type="numeric(5)" required="false" %}
Page number indexed from 1 | Ex:

`1`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Count" type="numeric(5)" required="false" %}
Count of details. Max count should be 100 | Ex:

`50`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fromRowId" type="" required="false" %}
To counter change in the search set, key to identify the last record for the previous set | Ex:

`20161061214556`
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

| **messageCode**                                | Y | numeric(4)  | Message code for statement inquiry response                                                                  | 1073                              |
| ---------------------------------------------- | - | ----------- | ------------------------------------------------------------------------------------------------------------ | --------------------------------- |
| **clientId**                                   | Y | string(15)  | Value copied from the request                                                                                | WIBMOBANK                         |
| **clientTxnId**                                | Y | string(100) | Value copied from the request                                                                                | 20150701235959xhstiesqfds         |
| **bankId**                                     | Y | numeric(4)  | Value copied from the request                                                                                | 1234                              |
| **responseDateTime**                           | Y | numeric(14) | Response date time in the format YYYYMMDDHHMMSS with time in 24 hr format                                    | 20161031214559                    |
| **Urn**                                        | Y | numeric(10) | A unique reference number for the card(urn)                                                                  | 1000058915                        |
| **customerId**                                 | Y | string(20)  | Value copied from the request                                                                                | IN2016201611                      |
| **accosaTransactionId**                        | Y | numeric(10) | Unique id for a particular transaction generated in Prepaid                                                  | 3591893                           |
| **responseCode**                               | Y | string(4)   | Contains the status of the transaction. 00 indicates success. Please refer Appendix for other response codes | 00                                |
| **responseMessage**                            | N | string(100) | Response message based on response code will be sent                                                         |                                   |
| **Description**                                | N | string(100) | Reserved field to send information to client                                                                 |                                   |
| **availableBalance**                           | Y | numeric(12) | Card available balance (implied decimals)                                                                    | 19000                             |
| **openingBalance**                             | Y | numeric(12) | Card opening balance (implied decimals)                                                                      | 19000                             |
| **closingBalance**                             | Y | numeric(12) | Card closing balance (implied decimals)                                                                      | 19000                             |
| **availableCashLimit**                         | Y | numeric(12) | Available Cash Limit on the card (implied decimals)                                                          | 110000                            |
| **pageNumber**                                 | N | numeric(5)  | Page number indexed from 1                                                                                   | 1                                 |
| **Count**                                      | N | numeric(5)  | Count of records returned                                                                                    | 50                                |
| **statementDetails.merchantName**              | Y | string(100) | Merchant at which the transaction took place                                                                 | Amazon Web Store                  |
| **statementDetails.transactionType**           | Y | string(10)  | 1.CR (Credit) 2.DR (Debit)                                                                                   | CR                                |
| **statementDetails.transactionAmount**         | Y | string(50)  | Amount of the transaction. Value will be in implied decimals                                                 | 10000                             |
| **statementDetails.transactionDate**           | Y | string(50)  | Date of the transaction in the format YYYY-MM-DD hh:mm:ss.S                                                  | 2017-02-06 14:26:34.611776        |
| **statementDetails.transactionNarration**      | N | string(500) | Used to store the clientTRNDescription for the request.                                                      | PG Load                           |
| **statementDetails.transactionClosingBalance** | Y | string(50)  | Closing balance at the end of each transaction. Value will be in implied decimals                            | 10000                             |
| **statementDetails.merchantCity**              | Y | string(50)  | City                                                                                                         | Bangalore                         |
| **statementDetails.transRefNumber**            | Y | string(50)  | Reference Number                                                                                             | 2016XYZ123                        |
| **statementDetails.rowId**                     | N | string(100) | Row Id to identify each row                                                                                  | 20161061214556                    |
| **statementDetails.eventId**                   | Y | string(50)  | event id's denotes the activity                                                                              | 303003                            |
| **statementDetails.stan**                      | N | string(30)  | SYSTEM\_TRACE\_AUDIT\_NUMBER                                                                                 | 019078                            |
| **statementDetails.rrn**                       | N | String(30)  | Retrieval Reference Number                                                                                   | 634405019078                      |
| **statementDetails.approvalCode**              | N | string(30)  | Approval Code                                                                                                | 9RQENE                            |
| **statementDetails.isMerchantTxn**             | N | Int         | Check for Merchant transaction                                                                               | 0/1 cmsEvents - 0, auth/settl – 1 |
| **statementDetails.clientTxnId**               | Y | string(100) | clientTxnId for cms events                                                                                   | 20150701235959xhstiesqfds         |
| **statementDetails.status**                    | N | String      | Statement status check. Kindly refer transaction Status tag at the top section for more details              | 0                                 |
| **statementDetails.authEpfTxnId**              | Y | string(50)  | Reference Number for Auth for corresponding settlement transactions                                          | 5616546                           |
| **statementDetails.authDate**                  | Y | string(50)  | auth Date for settlement transactions. Format - YYYY-MM-DD hh:mm:ss.S                                        | 2017-02-06 14:26:34.611776        |

{% tabs %}
{% tab title="Curl" %}
```json
Sample Statement Inquiry API Request
https://pp-sandbox.wibmo.com/api/v1/statementInquiry
Sample Request
Encrypted req->
{
"token":"Pl8F5kDZcvADIiursiAvvbHNuL9Wv5eaFdorGVFU6FKfIEnV/YskkzJlAov2ZHJWnqGNLOXfBq4SQqw8Ep4sK0gCAAkRXATCb1nSY6s=" 
}
// Sample token. Client will have to generate this token. 
Decrypted req->
{ 
    "messageCode": "1072",
    "clientId": "WibmoClient",
    "bankId": 1234,
    "requestDateTime": "20161221210608",
    "clientTxnId": "ccccfccs",
    "secureCode": "AfYtlO5kqdySIjXyNmGg3F",
    "last4Digits": "0930",
    "urn": 1000073787,
    "customerId": "QW149",
    "fromDate":"08/06/2015",
    "toDate": "30/06/2019",
    "pageNumber":"1",
    "count":"10",
    "fromRowId":"0"
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
  "urn": 1000073787,
  "customerId": "QW149",
  "responseCode": "00",
  "messageCode": 1073,
  "clientTxnId": "ccccfccs",
  "clientId": "WibmoClient",
  "responseDateTime": "20170207130012",
  "accosaTransactionId": 582411,
  "responseMessage": "SUCCESS",
  "bankId": 1234,
  "availableBalance": "1500",
  "openingBalance": "300",
  "closingBalance": "1500",
  "availableCashLimit": "0",
  "pageNumber": 1,
  "count": 10,
  "statementDetails": [
    {
      "merchantName": "Card Reload",
      "transactionType": "CR",
      "transactionAmount": "500",
      "transactionDate": "2017-02-07 12:58:46.002744",
      "transactionNarration": "Bill Pay",
      "transactionClosingBalance": "500s",
      "merchantCity": "",
      "transRefNumber": "3631878",
      "eventId": "303003",
      "rowId": 1486452526002,
      "rrn": "",
      "stan": "",
      "approvalCode": "",
      "isMerchantTxn": 0,
      "clientTxnId":"asdfasdfasdfsga",
      "status":""
    },
    {
      "merchantName": "Card Reload",
      "transactionType": "CR",
      "transactionAmount": "500",
      "transactionDate": "2017-02-06 15:12:17.501029",
      "merchantCity": "",
      "transRefNumber": "3631875",
      "eventId": "303003",
      "rowId": 1486374137501,
      "rrn": "",
      "stan": "",
      "approvalCode": "",
      "isMerchantTxn": 0,
      "clientTxnId":"asdfasdafaa",
      "status":""
    }
  ]
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
    "urn": 0, 
    "responseCode": "1332", 
    "messageCode": 3021, 
    "clientTxnId": "verifyCard000039", 
    "clientId": "WibmoClient", 
    "responseDateTime": "20220914200827", 
    "accosaTransactionId": 487106, 
    "responseMessage": "URN_MOBILE_EMAIL_MISSING_IN_REQUEST", 
    "bankId": 6040
}
</code></pre>
{% endtab %}
{% endtabs %}