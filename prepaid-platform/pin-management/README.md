---
description: >-
  This Module will be allowing the client/customer to set/reset PIN. This module
  will also contain API to validate PIN entered by the customer for
  authentication.
---

# PIN Management

This is mandatory module in case of Physical card issuance. It is recommended to utilize this module in case of Virtual Only Cards or Wallets for secure 2FA.

You can use the following APIs to perform PIN management on Prepaid Card/ Wallet for the customer:

<mark style="color:blue;">`Reset PIN API`</mark>

{% swagger method="post" path="" baseUrl="api/v1/mobileNumberBasedCardInquiry" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="x-api-key" type="String" required="true" %}
Will be shared along with access to Prepaid Platform Sandbox environment. | Ex. ABCDEF12345
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" type="String" required="true" %}
Request body will contain the encrypted token. Encryption will be done by the client using the client key provided by Wibmo Team. Encryption/ Decryption methodology - AES 256.

Note - Below are the request parameters in clear text that need to be encrypted by the client. The below parameters should not be shared in clear text.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="messageCode" type="Numeric(4)" required="true" %}
Code to Identify the mobile number inquiry request type API. | Ex.

`1930`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="clientId" type="String(15)" required="true" %}
Uniquely identifies the client. During program enrolment each client is provided with a unique client id by Prepaid System. | Ex.

`FintechA`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="clientTxnId" type="String(100)" required="true" %}
Unique Id generated by the client for each API call. | Ex.

`1234567`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requestDateTime" type="Numeric(14)" required="true" %}
Local Date and time stamp when the transaction originated from the client in YYYYMMDDHHMMSS with time in 24 hr format. | Ex. 19010101120000
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bankId" type="Numeric(4)" required="true" %}
Bank Id is provided by Prepaid platform during client onboarding to uniquely identify the card issuer. | Ex.

`1234`
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" type="Numeric(12)" name="cardHolderMobileNumber" %}
Card Holder Mobile number will be provided by customer during inquiry. Require 12 digit mobile number that includes the country code. | Ex.

`9198XXXXXXX8`
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

| ResponseCode                     | Type        | Mandatory | Description                                                                                                                                                                                                                                                              |
| -------------------------------- | ----------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| token                            | String      | Yes       | <p>Wibmo Prepaid system will share the response in an Encrypted format. Client will have to decrypt the response using client key. Encryption/ Decryption Methodology - AES 256<br>Note - Below are the response parameters that the client can see post decryption.</p> |
| messageCode                      | Numeric(4)  | Yes       | Message code for mobile number based inquiry response. Ex. 1931                                                                                                                                                                                                          |
| clientId                         | String(15)  | Yes       | Uniquely identifies the client in Prepaid Platform. Value copied from the request body. Ex. FintechA                                                                                                                                                                     |
| clientTxnId                      | String(100) | Yes       | A unique reference id generated by the client for each and every API call. Value copied from request body. Ex. 20150701235959xhstiesqfds                                                                                                                                 |
| bankId                           | Numeric(4)  | Yes       | Bank Id is provided by Prepaid Platform during client onboarding to uniquely identify the card issuer. Value copied from request body. Ex. 1234                                                                                                                          |
| responseDateTime                 | Numeric(14) | Yes       | Response date time in the format YYYYMMDDHHMMSS with time in 24 hr format. Ex. 20160101000000                                                                                                                                                                            |
| urn                              | Numeric(10) | Yes       | A unique reference number for the card generated by Prepaid system. Ex. 1000000005                                                                                                                                                                                       |
| customerId                       | String(20)  | Yes       | Customer ID generated by client to uniquely identify the customer. This value is copied from the request body. Ex. IN0000000001                                                                                                                                          |
| accosaTransactionId              | Numeric(10) | Yes       | Unique id for a particular transaction generated in Prepaid Platform. Ex. 3000003                                                                                                                                                                                        |
| responseCode                     | String(4)   | Yes       | Contains the status of the transaction. 00 indicates success. Please refer below for other response codes                                                                                                                                                                |
| responseMessage                  | String(100) | No        | Response message based on response code will be sent. Ex. Mobile based Inquiry successful.                                                                                                                                                                               |
| description                      | String(100) | No        | Reserved field to send information to client. Ex. Mobile based Inquiry successful.                                                                                                                                                                                       |
| availableBalance                 | Numeric(12) | Yes       | Card available balance (implied decimals). Ex. 19000                                                                                                                                                                                                                     |
| cardStatus                       | String(2)   | Yes       | Status of card like Active, etc. \| Ex. 0                                                                                                                                                                                                                                |
| cardHolder.cardProfileId         | Numeric(2)  | Yes       | This indicates the type of KYC done for the customer. 200 - Low KYC; 1 - Min KYC; 150 - Full KYC                                                                                                                                                                         |
| cardHolder.cardholderMobile      | Numeric(20) | No        | Mobile number of the card holder. Ex. 98XXXXXX89                                                                                                                                                                                                                         |
| cardHolder.cardholderFirstName   | String(100) | No        | First Name of the card holder. Ex. Vivek                                                                                                                                                                                                                                 |
| cardHolder.cardholderDateOfBirth | String(15)  | Yes       | Date of birth of the card holder. Ex. 01-01-1900                                                                                                                                                                                                                         |
| kycName                          | String(100) | Yes       | This field will contain card Profile name (KYC/NON-KYC, etc.) Ex. MIN\_KYC, FULL\_KYC, LOW\_KYC                                                                                                                                                                          |
| last4Digits                      | String(4)   | Yes       | Last 4 digits of the card number. Ex. 0000                                                                                                                                                                                                                               |
| entityName                       | String(50)  | No        | PPI Entity Name. \| Ex. WibmoBank                                                                                                                                                                                                                                        |
| clientName                       | String(50)  | No        | Wallet client for the program. Ex. FintechA                                                                                                                                                                                                                              |
| programName                      | String(50)  | No        | Program Name to identity the program/channel through which the request was received. Ex. FintechA                                                                                                                                                                        |

{% tabs %}
{% tab title="Curl" %}
URL: [https://pp-sandbox.wibmo.com/api/v1/mobileNumberBasedCardInquiry](https://pp-sandbox.wibmo.com/api/v1/mobileNumberBasedCardInquiry)

```
Encrypt request:
{
    "token": "+9afBR5Ul+/Vrryg75yrucw7gfynw47g3ik" // Sample token. Client will have to generate this token. 
}
Decrypted request:
{
    "messageCode": 1930,
    "clientId": "FintechA",
    "secureCode": "AfYtlO5kqdySIjXyNmGg3F",
    "clientTxnId": "207507271458370149gM90jY73",
    "requestDateTime":"20210916040820",
    "bankId": 2010,
    "cardHolderMobileNumber":"919999999999"
}
```
{% endtab %}

{% tab title="Response" %}
Sample Mobile number based inquiry response

```
Encrypted Response-> 
{ 
"token":"54rtyegdhetrVr+gt06szxIlMRF77feLEznU116YCh/3FUk" //Sample token. Client will have to decrypt the token shared in the response body
} 

Decrypted Response->
{
    "urn": 68,
    "customerId": "swa__sandbox_002",
    "description": "Active",
    "responseCode": "00",
    "messageCode": 1931,
    "clientTxnId": "207507271458370149gM90jY73",
    "clientId": "FintechA",
    "responseDateTime": "20220404134941",
    "accosaTransactionId": 0,
    "responseMessage": "SUCCESS",
    "bankId": 2010,
    "availableBalance": "559941",
    "cardStatus": "0",
    "cardHolder": {
        "cardProfileId": 1,
        "cardholderFirstName": "First",
        "cardholderLastName": "Last",
        "cardholderMobile": "919999999999",
        "cardholderEmail": "firstname.lastname@email.com",
        "cardholderAddress": "wings, MG Road",
        "cardholderCity": "Bangalore",
        "cardholderState": "karnataka",
        "cardholderCountry": "India",
        "cardholderZipCode": "560007",
        "cardholderDateOfBirth": "01-Jan-2001"
    },
    "kycName": "MIN_KYC",
    "last4Digits": "9017",
    "entityName": "EName",
    "clientName": "CName",
    "programName": "e_wallet"
}
```
{% endtab %}
{% endtabs %}

| responseCode | responseReason                               |
| ------------ | -------------------------------------------- |
| 00           | Success                                      |
| 1001         | CARD NOT FOUND                               |
| 1030         | INVALID MESSAGE(if mobile number is missing) |
| 1237         | DUPLICATE PHONE NUMBER WITH MULTIPLE ACCOUNT |
| 1501         | SYSTEM ERROR (Database Error)                |
| 1500         | SYSTEM ERROR                                 |
