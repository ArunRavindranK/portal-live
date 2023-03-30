# Version Request API - pVrq

ThreeDSRequestor(merchant, Payment Aggregator) does a version request to 3DS Server application, for checking whether the BIN is enable for 1.0 or 2.0 version

This api needs to be initiated by ThreeDSRequestor

{% hint style="danger" %}
acquirerID needs to be appended in every URL.
{% endhint %}

{% swagger method="post" path="" baseUrl="/3dsserverapi/v3/pVrq/<acquirerID>" summary="Version Request" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="messageType" type="String (8) " required="true" %}
pVrq
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceChannel" type="String (2)" required="true" %}
01 = App-based (APP) 02 = Browser (BRW) 03 = 3DS Requestor Initiated (3RI)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="p_messageVersion" type="String (8)" required="true" %}
Customer Protocol version
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantTransID" type="String (36)" required="true" %}
Unique Transaction Identifier for merchant / PG
{% endswagger-parameter %}

{% swagger-parameter in="body" name="acctNumber" type="String (19)" required="true" %}
Card number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="acquirerBIN" type="String (6)" required="true" %}
Acquirer BIN assigned by Scheme
{% endswagger-parameter %}

{% swagger-parameter in="body" name="acquirerID" type="String (4)" required="true" %}
Acquirer Identifier assigned by 3DS Server / MPI
{% endswagger-parameter %}

{% swagger-parameter in="body" name="threeDSRequestorMethodNotificationRespURL" type="String (2048)" required="true" %}
Merchant URL that will receive the notification of 3DS Method completion from the ACS.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "messageType": "pVrs",
    "deviceChannel": "02",
    "p_messageVersion": "2.1.0",
    "acsStartVersion": "2.0.1",
    "acsEndVersion": "2.2.0",
    "dsStartVersion": "2.0.1",
    "dsEndVersion": "2.2.0",
    "merchantTransID": "54c8fefe-e694-3569-7864-d4329ce60971",
    "threeDSServerPaRqURL": "https://<sandbox.com>/3dsserverapi/v3/pArq/indblr-blrrel/7000",
    "threeDSServerTransID": "df55dab7-8ca3-4d12-8836-9fd806cd8374",
    "threeDSACSMethodURL": "https://<acssandbox.com>/v1/acs/services/threeDSMethod/9111?cardType=V",
    "threeDSJSBrowserDetailFetchURL": "https://<sandbox.com>/static/v3/browser.js",
    "threeDSMethodDataFormPost": {
        "threeDSMethodData": "eyJ0aHJlZURTU2VydmVyVHJhbnNJRCI6ImRmNTVkYWI3LThjYTMtNGQxMi04ODM2LTlmZDgwNmNkODM3NCIsInRocmVlRFNNZXRob2ROb3RpZmljYXRpb25VUkwiOiJodHRwczovL21lcmNoYW50c2VjdXJlLmNvbS9mZXRjaE5vdGlmaWNhdGlvblJlcXVlc3QifQ=="
    },
    "acsInfoInd": [
        "01",
        "02",
        "03",
        "04",
        "80"
    ],
    "scheme": "VISA",
    "errorCode": "000"
}
```
{% endswagger-response %}
{% endswagger %}

#### Response Details

| Response Body                               | Data Type         | Length                            | Field Description                                                                                                                                                                                                                                                                                    |
| ------------------------------------------- | ----------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| messageType                                 | String            | Variable, 5–8 characters          | Identifies the Message Type                                                                                                                                                                                                                                                                          |
| deviceChannel                               | String            | 2 characters                      | 01 = App-based (APP) 02 = Browser (BRW) 03 = 3DS Requestor Initiated (3RI)                                                                                                                                                                                                                           |
| p\_messageVersion                           | String            | Variable, 5–8 characters          | Customer Protocol version                                                                                                                                                                                                                                                                            |
| acsStartVersion                             | String            | Variable, 5–8 characters          | Earliest Bin supported EMVCo Protocol Version at ACS                                                                                                                                                                                                                                                 |
| acsEndVersion                               | String            | Variable, 5–8 characters          | Latest Bin supported EMVCo Protocol Version at ACS.                                                                                                                                                                                                                                                  |
| dsStartVersion                              | String            | Variable, 5–8 characters          | Earliest Bin supported EMVCo Protocol Version at DS                                                                                                                                                                                                                                                  |
| dsEndVersion                                | String            | Variable, 5–8 characters          | Latest Bin supported EMVCo Protocol Version at DS                                                                                                                                                                                                                                                    |
| scheme                                      | String            | Variable, 5–8 characters          | Identifies the Card Scheme                                                                                                                                                                                                                                                                           |
| directoryServerID                           | String            | Variable,250 characters           | Directory Server ID of the Scheme of Public Key for device encryption by the SDK                                                                                                                                                                                                                     |
| acsInfoInd                                  | Json String Array | 2 characters                      | Provides the information of ACS - • 01 =Authentication Available at ACS • 02 = Attempts Supported by ACS or DS • 03 = Decoupled Authentication Supported • 04 = Whitelisting Supported • 05–79 = Reserved for EMVCo future use (Values invalid until defined by EMVCo) • 80–99 = Reserved for DS use |
| merchantTransID                             | String            | Length: 36 characters             | Unique Transaction Identifier for merchant / PG                                                                                                                                                                                                                                                      |
| threeDSServerTransID                        | String            | Length: 36 characters             | 3DS Server Unique Transaction ID                                                                                                                                                                                                                                                                     |
| threeDSServerPaRqURL                        | String            | Length:2048 characters            | URL to post pArq request                                                                                                                                                                                                                                                                             |
| threeDSACSMethodURL                         | String            | Length:2048 characters            | URL to initiate ACS Method URL                                                                                                                                                                                                                                                                       |
| threeDSJSBrowserDetailFetchURL              | String            | Length:2048 characters            | URL to fetch Browser Details                                                                                                                                                                                                                                                                         |
| threeDSMethodDataFormPost                   | Object            |                                   | 3DS Server ACS method URL form data                                                                                                                                                                                                                                                                  |
| threeDSMethodDataFormPost.threeDSMethodData | String            |                                   | Base64 URL encoded value of threeDSMethod Data to be posted to ACS.                                                                                                                                                                                                                                  |
| errorCode                                   | String            | 3 characters, numeric             | 000- Success 001-999 error codes will be sent basis the validation.                                                                                                                                                                                                                                  |
| error Desc                                  | String            | Variable, maximum 2048 characters | Error Description                                                                                                                                                                                                                                                                                    |

### Sample pVrq 2.0 API request and response

{% tabs %}
{% tab title="Sample Curl Request" %}
```
curl --location --request POST 'https://<sandbox.com>/3dsserverapi/v3/pVrq/7000' \
--header 'Content-Type: application/json' \
--data-raw '{
  "messageType": "pVrq",
  "deviceChannel": "02",
  "p_messageVersion": "2.1.0", 
  "merchantTransID": "54c8fefe-e694-3569-7864-d4329ce60971",    
  "acctNumber": "XXXXXXXXXXXXXXXX",   
  "signatureHashIdentifier":"02",
  "acquirerBIN": "511111", 
  "acquirerID" :"7000",
  "threeDSRequestorMethodNotificationRespURL": "https://merchantsecure.com/fetchNotificationRequest"
}'
```
{% endtab %}

{% tab title="Sample Response" %}
```
{
    "messageType": "pVrs",
    "deviceChannel": "02",
    "p_messageVersion": "2.1.0",
    "acsStartVersion": "2.0.1",
    "acsEndVersion": "2.2.0",
    "dsStartVersion": "2.0.1",
    "dsEndVersion": "2.2.0",
    "merchantTransID": "54c8fefe-e694-3569-7864-d4329ce60971",
    "threeDSServerPaRqURL": "https://<sandbox.com>/3dsserverapi/v3/pArq/indblr-blrrel/7000",
    "threeDSServerTransID": "df55dab7-8ca3-4d12-8836-9fd806cd8374",
    "threeDSACSMethodURL": "https://<acssandbox.com>/v1/acs/services/threeDSMethod/9111?cardType=V",
    "threeDSJSBrowserDetailFetchURL": "https://<sandbox.com>/static/v3/browser.js",
    "threeDSMethodDataFormPost": {
        "threeDSMethodData": "eyJ0aHJlZURTU2VydmVyVHJhbnNJRCI6ImRmNTVkYWI3LThjYTMtNGQxMi04ODM2LTlmZDgwNmNkODM3NCIsInRocmVlRFNNZXRob2ROb3RpZmljYXRpb25VUkwiOiJodHRwczovL21lcmNoYW50c2VjdXJlLmNvbS9mZXRjaE5vdGlmaWNhdGlvblJlcXVlc3QifQ=="
    },
    "acsInfoInd": [
        "01",
        "02",
        "03",
        "04",
        "80"
    ],
    "scheme": "VISA",
    "errorCode": "000"
}
```
{% endtab %}
{% endtabs %}
