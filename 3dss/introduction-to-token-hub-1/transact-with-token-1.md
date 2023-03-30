# Final Authentication Status Request - pRqFrq

For Challenge Browser flow ThreeDSRequestor will initiate below request to fetch Authentication value, eci and Transaction status of the transaction with 3DS Server.

pRqFrq needs to be posted to the URL from field "authenticationUrl" of "pArq api" response

{% hint style="danger" %}
acquirerID needs to be appended in every request.

merchant-name needs to be appended in every request.
{% endhint %}

{% swagger method="post" path="" baseUrl="/3dsserverapi/legacy/fetchAuth/<merchantName>/ <acquirerID>" summary="Final result request" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="messageType" type="String (8)" required="true" %}
pRqFrq
{% endswagger-parameter %}

{% swagger-parameter in="body" name="p_message Version" type="String (8)" required="true" %}
Message Protocol Version Number of the specification
{% endswagger-parameter %}

{% swagger-parameter in="body" name="messageVersion" type="String (8)" required="true" %}
EMVCo Protocol Version Number of the specification
{% endswagger-parameter %}

{% swagger-parameter in="body" name="threeDSServerTransID" type="String (36)" required="true" %}
3DS Server Unique Transaction ID
{% endswagger-parameter %}

{% swagger-parameter in="body" type="String (36)" name="acsTransID" required="true" %}
ACS Server Unique Transaction ID
{% endswagger-parameter %}

{% swagger-parameter in="body" type="String (36)" name="dsTransID" required="false" %}
DS Server Unique Transaction ID
{% endswagger-parameter %}

{% swagger-parameter in="body" type="String (36)" name="merchantTransID" required="true" %}
Merchant Server Unique Transaction ID
{% endswagger-parameter %}

{% swagger-parameter in="body" type="String (36)" name="sdkTransID" required="true" %}
SDK Server Unique Transaction ID, field is required only for SDK In App transaction for 2.0.1 version and beyond
{% endswagger-parameter %}

{% swagger-parameter in="body" name="acquirerID" type=" String (4)" required="true" %}
Acquirer Identifier assigned by 3DSS / MPI
{% endswagger-parameter %}

{% swagger-parameter in="body" name="acsAuthResponse" type="String" required="false" %}
Base64 URL Encoded PaRes or cRes data received from ACS.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="messageExtension" type="JSON Data Type:Array" required="false" %}
Data necessary to support requirements, not otherwise defined in the 3-D Secure message is carried in a Message Extension.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "messageVersion": "1.1.0",
  "messageType": "pRsFr",
  "threeDSServerTransID": "88c460b7-b0b4-473d-bbd6-c7a0189c0178",
  "acsTransID": "3123dfb0-83fa-11ec-9f85-19877563145b",
  "dsTransID": "fccd4a07-d376-4e4e-8600-9f8033bb6b46",
  "merchantTransID": "10d17e476cde3f7a9b0ac6c0c8a07b825282f2afa75c271be1922a1b2f657facf2205dc301d4256cde89707704aecca7|3dc2d52c94f2a2da841f09111a1fe2c739ac6eba",
  "eci": "05",
  "authenticationValue": "AAIBAhGFVxI0VngjYIVXAAAAAAA=",
  "transStatus": "Y",
  "errorCode": "000",
  "errorDesc": "",
  "pmessageVersion": "1.1.0"
}
```
{% endswagger-response %}
{% endswagger %}

#### Response Details

| Response Body        | Data Type | Field Length                          | Field Description                                                                             |
| -------------------- | --------- | ------------------------------------- | --------------------------------------------------------------------------------------------- |
| messageType          | String    | Variable, 5–8 characters28 characters | Identifies the Message Type. Ex: pRsFr                                                        |
| p\_messageVersion    | String    | Variable, 5–8 characters              | Message Protocol Version Number of the specification                                          |
| messageVersion       | String    | Variable, 5–8 characters              | EMVCo Protocol Version Number of the specification                                            |
| threeDSServerTransID | String    | 36 characters                         | 3DS Server Unique Transaction ID                                                              |
| acsTransID           | String    | 36 characters                         | ACS Server Unique Transaction ID                                                              |
| dsTransID            | String    | 36 characters                         | DS Server Unique Transaction ID                                                               |
| merchantTransID      | String    | 36 characters                         | Merchant Server Unique Transaction ID                                                         |
| sdkTransID           | String    | 36 characters                         | SDK Server Unique Transaction ID                                                              |
| eci                  | String    | 2 characters                          | As per EMVCo / DS specs                                                                       |
| authenticationValue  | String    | 28 characters                         | Payment System-specific value provided as part of the ACS registration for each supported DS. |
| transStatus          | String    | 1 character                           | As per EMVCo spec                                                                             |
| errorCode            | String    | 1 character                           | 000- Success 001-999 error codes will be sent basis the validation                            |
| errorDesc            | String    | Variable, maximum 2048 characters     | Error Description                                                                             |

### **pRqFrq 1.0 : Request for fetching CAVV and eci**

{% tabs %}
{% tab title="Curl" %}
```
curl --location --request POST 'https://<sandbox.com>/3dsserverapi/legacy/fetchAuth/indblr-blrrel/7000' \
--header 'Content-Type: application/json' \
--header 'Cookie: __cfruid=f832cc2d74cb1e13fd4b3141780cca33d787b82e-1648729230' \
--data-raw '{
    "messageType": "pRqFrq",
    "messageVersion": "1.0.2",    
    "p_messageVersion": "1.0.2",
    "threeDSServerTransID": "383a4443-28c5-42c1-a87f-85916059359f",
    "acsTransID": "202104060931251821dT9mT5jP",
    "dsTransID": "",
    "sdkTransID": "",       
    "merchantTransID": "54c8fefe-e694-3569-7864-d4329ce60971",
    "signatureHashIdentifier":"02",
    "acquirerID":"7000",
    "paRes":null,
    "acsAuthResponse": "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"
}'
```
{% endtab %}

{% tab title="Response" %}
```
{
  "messageVersion": "1.1.0",
  "messageType": "pRsFr",
  "threeDSServerTransID": "88c460b7-b0b4-473d-bbd6-c7a0189c0178",
  "acsTransID": "3123dfb0-83fa-11ec-9f85-19877563145b",
  "dsTransID": "fccd4a07-d376-4e4e-8600-9f8033bb6b46",
  "merchantTransID": "10d17e476cde3f7a9b0ac6c0c8a07b825282f2afa75c271be1922a1b2f657facf2205dc301d4256cde89707704aecca7|3dc2d52c94f2a2da841f09111a1fe2c739ac6eba",
  "eci": "05",
  "authenticationValue": "AAIBAhGFVxI0VngjYIVXAAAAAAA=",
  "transStatus": "Y",
  "errorCode": "000",
  "errorDesc": "",
  "pmessageVersion": "1.1.0"
}
```
{% endtab %}
{% endtabs %}
