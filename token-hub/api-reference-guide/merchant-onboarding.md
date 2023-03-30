# Merchant Onboarding

Merchant onboarding is an essential step before the tokenization flow begins. Merchants are onboarded using this API on the card networks. Token requestor id is created and returned to the merchants. Token requestor id is used for tokenization transaction.

{% swagger method="post" path="" baseUrl="/usr/cardVault/networkToken/v1/100001/merchantOnboard" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-Auth-Token" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="clientId" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="clientApiUser" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="clientApiKey" required="true" %}

{% endswagger-parameter %}
{% endswagger %}

#### Sample Request

{% tabs %}
{% tab title="Curl" %}
```
curl --location --request POST 'http://<sandbox>/tokenVault/nts/v1/merchant/onboard' \
--header 'X-Auth-Token: CAD859AE25FE5CF6D18EB33526C2C077D1A2F7333073D7C467E36132DC50AE61' \
--header 'clientId: f3fc8d54-ad20-4474-b746-8bb29009ac11' \
--header 'clientApiUser: 100001-PayU-7hE6lE3nI9' \
--header 'clientApiKey: PayU7ep0m3480T' \
--header 'Content-Type: application/json' \
--data-raw '{
    "serviceContext": "TOKENIZATION",
    "companyPrimaryLegalName": "Company1",
    "companyPrimaryTradeName": "Company1",
    "primaryWebsiteURL": "https://www.xxx.com",
    "companyCity": "Bangalore",
    "companyCountryCode": "IN",
    "primaryContactEmail": "yyy@xxx.com",
    "businessIdentificationType": "PAN",
    "businessIdentificationValue": "123456567",
    "relationships": [
        {
            "externalClientId": "Wibmo-PayU-MTF-Merchant"
        }
    ],
    "cardType":"V"
}'
```
{% endtab %}

{% tab title="Response" %}
```
{
    "statusCode": "MCS000",
    "errorDesc": null,
    "status": "Success",
    "msg": "Successfully Created",
    "transactionId": null,
    "tokenRequestorID": "445566700081",
    "trTSPCLientId": "234f572d0-8464-2ed3-4071-1312659dee02",
    "relationships": [
        {
            "externalClientId": "TRTSP-Merchant1"
        }
    ],
    "merchantStatus": "ACTIVE"
} 
```
{% endtab %}
{% endtabs %}
