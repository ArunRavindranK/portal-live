---
description: Update merchant
---

# Update merchant



{% swagger method="post" path="" baseUrl="<domain>/merchants/onboarding/update/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER " type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="allowedIP" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="appId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardMaskPattern" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardPaymentsAllowed" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="chargeLater" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="checksumKey" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="createdDate" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="currencyCode" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="debugMode" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="dynamicMerchant" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="instantCBAllowedTime" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="instantCBEnabled" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="internalMerchant" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="itpMerchantHashKey" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="itpMerchantId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="itpMerchantName" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCategoryCode" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantName" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantPCICertified" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantReturnUrl" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="nbPaymentsAllowed" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="pgHashKey" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="pgImplId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="pgInstanceId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="pgLoginId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="pgMerchantId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="pgTid" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="postfix" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="prefix" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="recurringPaymentUpdateeUrl" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="recurringPaymentsAllowed" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="restrictedPaymentTypes" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="threeDSMerchantHashKey" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="threeDSMerchantName" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="tokenExpiryInMins" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="updatedDate" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="upiPaymentsAllowed" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="walletPaymentsAllowed" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
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

{% swagger-response status="403: Forbidden" description="" %}
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
{% endswagger %}

{% tabs %}
{% tab title="Sample curl command" %}
curl --location --request POST '/payments/merchants/onboarding/update' --header 'Content-Type: application/json' --header 'X-API-TOKEN:replace\_with\_basic\_auth\_to\_be\_built\_by\_client' --data-raw'{ "allowedIP": "string", "appId": "string", "cardMaskPattern": "string", "cardPaymentsAllowed": true, "chargeLater": true, "checksumKey": "string", "countryCode": "string", "createdDate": "2022-06-28T11:49:49.152Z", "currencyCode": "string", "debugMode": true, "dynamicMerchant": true, "instantCBAllowedTime": 0, "instantCBEnabled": true, "internalMerchant": true, "itpMerchantHashKey": "string", "itpMerchantId": "string", "itpMerchantName": "string", "merchantCategoryCode": "string", "merchantId": "string", "merchantName": "string", "merchantPCICertified": true, "merchantReturnUrl": "string", "nbPaymentsAllowed": true, "pgHashKey": "string", "pgImplId": 0, "pgInstanceId": "string", "pgLoginId": "string", "pgMerchantId": "string", "pgTid": "string", "postfix": "string", "prefix": "string", "recurringPaymentUpdateeUrl": "string", "recurringPaymentsAllowed": true, "restrictedPaymentTypes": "string", "status": 0, "threeDSMerchantHashKey": "string", "threeDSMerchantName": "string", "threeDSdsMerchantId": "string", "tokenExpiryInMins": 0, "updatedDate": "2022-06-28T11:49:49.153Z", "upiPaymentsAllowed": true, "walletPaymentsAllowed": true }'
{% endtab %}

{% tab title="Request" %}
```
{
  "allowedIP": "string",
  "appId": "string",
  "cardMaskPattern": "string",
  "cardPaymentsAllowed": true,
  "chargeLater": true,
  "checksumKey": "string",
  "countryCode": "string",
  "createdDate": "2022-06-28T11:49:49.152Z",
  "currencyCode": "string",
  "debugMode": true,
  "dynamicMerchant": true,
  "instantCBAllowedTime": 0,
  "instantCBEnabled": true,
  "internalMerchant": true,
  "itpMerchantHashKey": "string",
  "itpMerchantId": "string",
  "itpMerchantName": "string",
  "merchantCategoryCode": "string",
  "merchantId": "string",
  "merchantName": "string",
  "merchantPCICertified": true,
  "merchantReturnUrl": "string",
  "nbPaymentsAllowed": true,
  "pgHashKey": "string",
  "pgImplId": 0,
  "pgInstanceId": "string",
  "pgLoginId": "string",
  "pgMerchantId": "string",
  "pgTid": "string",
  "postfix": "string",
  "prefix": "string",
  "recurringPaymentUpdateeUrl": "string",
  "recurringPaymentsAllowed": true,
  "restrictedPaymentTypes": "string",
  "status": 0,
  "threeDSMerchantHashKey": "string",
  "threeDSMerchantName": "string",
  "threeDSdsMerchantId": "string",
  "tokenExpiryInMins": 0,
  "updatedDate": "2022-06-28T11:49:49.153Z",
  "upiPaymentsAllowed": true,
  "walletPaymentsAllowed": true
}

```
{% endtab %}

{% tab title="Response" %}
200 -> OK&#x20;

201 --> Created&#x20;

401 -> Unauthorized&#x20;

403 -> Forbidden&#x20;

404 -> Not Found
{% endtab %}
{% endtabs %}
