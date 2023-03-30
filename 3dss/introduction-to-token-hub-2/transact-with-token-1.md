# Final Authentication Status Request - pRqFrq

For Challenge Browser flow ThreeDSRequestor will initiate below request to fetch Authentication value, eci and Transaction status of the transaction with 3DS Server.

pRqFrq needs to be posted to the URL from field "authenticationUrl" of "pArq api" response.

{% hint style="danger" %}
acquirerID needs to be appended in every request.

merchant-name needs to be appended in every request.
{% endhint %}

{% swagger method="post" path="" baseUrl="/3dsserverapi/v3/pRqFrq/<merchantName>/ <acquirerID>" summary="Final result request" %}
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
```json
{
  "messageVersion": "2.1.0",
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
  "pmessageVersion": "2.1.0"
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

### **pRqFrq : Request for fetching CAVV and eci 2.0**

{% tabs %}
{% tab title="Curl" %}
```
curl --location --request POST 'https://<sandbox.com>/3dsserverapi/v3/pRqFrq/indblr-blrrel/7000' \
--header 'Content-Type: application/json' \
--header 'Cookie: __cfruid=f832cc2d74cb1e13fd4b3141780cca33d787b82e-1648729230' \
--data-raw '{
  "messageType": "pRqFr",
  "messageVersion": "2.1.0",
  "threeDSServerTransID": "df55dab7-8ca3-4d12-8836-9fd806cd8374",
  "merchantTransID": "10d17e476cde3f7a9b0ac6c0c8a07b825282f2afa75c271be1922a1b2f657facf2205dc301d4256cde89707704aecca7|3dc2d52c94f2a2da841f09111a1fe2c739ac6eba",
  "signatureHashIdentifier": "null",
  "acquirerID": "7000",
  "acsAuthResponse": "eyJ0aHJlZURTU2VydmVyVHJhbnNJRCI6Ijg4YzQ2MGI3LWIwYjQtNDczZC1iYmQ2LWM3YTAxODljMDE3OCIsImFjc1RyYW5zSUQiOiIzMTIzZGZiMC04M2ZhLTExZWMtOWY4NS0xOTg3NzU2MzE0NWIiLCJtZXNzYWdlVHlwZSI6IkNSZXMiLCJtZXNzYWdlVmVyc2lvbiI6IjIuMS4wIiwiYWNzVWlUeXBlIjoiMDEiLCJjaGFsbGVuZ2VDb21wbGV0aW9uSW5kIjoiWSIsImlzc3VlckltYWdlIjp7ImhpZ2giOiJodHRwczovL2FjY29zYS1pdnMuczMuYXAtc291dGgtMS5hbWF6b25hd3MuY29tL2FjY29zYS1pdnMvdjEvcGFydGljaXBhbnQvYWRpYmJrL2ltYWdlcy9hZGliYmtfbG9nby5qcGciLCJleHRyYUhpZ2giOiJodHRwczovL2FjY29zYS1pdnMuczMuYXAtc291dGgtMS5hbWF6b25hd3MuY29tL2FjY29zYS1pdnMvdjEvcGFydGljaXBhbnQvYWRpYmJrL2ltYWdlcy9hZGliYmtfbG9nby5qcGciLCJtZWRpdW0iOiJodHRwczovL2FjY29zYS1pdnMuczMuYXAtc291dGgtMS5hbWF6b25hd3MuY29tL2FjY29zYS1pdnMvdjEvcGFydGljaXBhbnQvYWRpYmJrL2ltYWdlcy9hZGliYmtfbG9nby5qcGcifSwicHNJbWFnZSI6eyJoaWdoIjoiaHR0cHM6Ly9hY2Nvc2EtaXZzLnMzLmFwLXNvdXRoLTEuYW1hem9uYXdzLmNvbS9hY2Nvc2EtaXZzL3YxL2Vtdi92aXNhL2ltYWdlcy92aXNhX2xvZ28uanBnIiwiZXh0cmFIaWdoIjoiaHR0cHM6Ly9hY2Nvc2EtaXZzLnMzLmFwLXNvdXRoLTEuYW1hem9uYXdzLmNvbS9hY2Nvc2EtaXZzL3YxL2Vtdi92aXNhL2ltYWdlcy92aXNhX2xvZ28uanBnIiwibWVkaXVtIjoiaHR0cHM6Ly9hY2Nvc2EtaXZzLnMzLmFwLXNvdXRoLTEuYW1hem9uYXdzLmNvbS9hY2Nvc2EtaXZzL3YxL2Vtdi92aXNhL2ltYWdlcy92aXNhX2xvZ28uanBnIn0sInRyYW5zU3RhdHVzIjoiWSIsImFjc0NvdW50ZXJBdG9TIjoiMDAwIiwicmVzZW5kRmxhZyI6Ik4ifQ",
  "p_messageVersion": "2.1.0"
}'
{
  "messageVersion": "2.1.0",
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
  "pmessageVersion": "2.1.0"
}
```
{% endtab %}

{% tab title="Response" %}
```
{
  "messageVersion": "2.1.0",
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
  "pmessageVersion": "2.1.0"
}
```
{% endtab %}
{% endtabs %}
