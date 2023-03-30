---
description: >-
  Once the verification request has been finished, this API is called which
  gives all the major details related with the transaction to evaluate the risk
  associated with the it.
---

# Payment Request API

{% swagger method="post" path="/request" baseUrl="http://trident.pc.enstage-sas.com/trident/analyse" summary="Payment Request" %}
{% swagger-description %}
Below are the specifications for consuming REST API. Request Data and Response are mentioned below along with sample values
{% endswagger-description %}

{% swagger-parameter in="header" name="x-api-key" required="true" %}
To be shared at the time of onboarding
{% endswagger-parameter %}

{% swagger-parameter in="body" name="instanceId" required="true" %}
Created and communicated to Client by Trident
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channelId" required="true" %}
Defines the mode of transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="async" required="true" %}
This parameter’s value determines if the communication between Trident and Client is synchronous or asynchronous.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="details" required="true" type="Boolean" %}
The detailed Trident evaluation summary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnSourceType" required="true" %}
Type of transaction source/event.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="acctNumber" required="true" %}
Primary identification of user eg: card number or bank acct. number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="clientId" required="true" %}
This field is available in response of Verification Request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="emailId" required="false" %}
Customer's email id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="partRequest" required="true" type="Boolean" %}
Its value determines if complete data for evaluation is passed in that request or it is the part of data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lastDrop" required="true" type="Boolean" %}
Its value determines if that request is the last part of the data coming in or not
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCountryCode" required="false" %}
Country Code of the Merchant. The same value must be used in the authorization
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sourceCurrencyCode" required="false" %}
Card issuer's bank currency
{% endswagger-parameter %}

{% swagger-parameter in="body" name="acquirerMerchantID" required="false" %}
Acquirer-defined merchant identifier
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantName" required="false" %}
Acquirer-defined merchant identifier
{% endswagger-parameter %}

{% swagger-parameter in="body" name="purchaseAmount" required="false" %}
Purchase amount in minor units of currency with all punctuation removed.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="purchaseDate" required="false" %}
Date and time of the purchase, expressed in UTC.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobileNo" required="false" %}
Customer's mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="false" %}
Max = 16 characters
{% endswagger-parameter %}

{% swagger-parameter in="body" name="messageType" required="false" %}
Type of the request message
{% endswagger-parameter %}

{% swagger-parameter in="body" name="purchaseCurrency" required="false" %}
Currency in which purchase amount is expressed
{% endswagger-parameter %}

{% swagger-parameter in="body" name="browserAcceptHeader" required="false" %}
Eg: "text/html, application/xhtml+xml, application/xml"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="browserJavaEnabled" type="Boolean" required="false" %}
Weather Java is enabled on the browser or not
{% endswagger-parameter %}

{% swagger-parameter in="body" name="browserLanguage" required="false" %}
Language configuration of the browser
{% endswagger-parameter %}

{% swagger-parameter in="body" name="browserColorDepth" required="false" %}
The number of bits used to hold a screen pixel eg: 32 or 24
{% endswagger-parameter %}

{% swagger-parameter in="body" name="browserScreenHeight" required="false" %}
Total height of the browser's screen
{% endswagger-parameter %}

{% swagger-parameter in="body" name="browserScreenWidth" required="false" %}
Total width of the browser's
{% endswagger-parameter %}

{% swagger-parameter in="body" name="browserTZ" required="false" %}
Time Zone of the browser
{% endswagger-parameter %}

{% swagger-parameter in="body" name="browserUserAgent" required="false" %}
What type of browser is being used.

Eg: "User-Agent: Mozilla /5.0"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" required="false" %}
Eg: "OTP_AUTH" or "browser"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="operatingSystem" required="false" %}
Operating system for where the transaction was initiated
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantCity" required="false" %}
Registered city for the merchant
{% endswagger-parameter %}

{% swagger-parameter in="body" name="timeStamp" required="false" %}
Time of transaction
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Validation Error : Invalid Card No, PAR or missing mandatory fields." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal Server Error" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="503: Service Unavailable" description="There was a timeout processing the request" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

#### Response Fields:

| Atrributes | Data Type | Description                                                           |
| ---------- | --------- | --------------------------------------------------------------------- |
| clientId   | String    | Unique Id generated by Trident for every transaction                  |
| NodeId     | String    | It is the identifier for Trident node which processes the transaction |

| Attribute          | Data Type | Description                                          |
| ------------------ | --------- | ---------------------------------------------------- |
| ruleRating         | Integer   | The total Score given to the Transaction             |
| clientId           | String    | Unique Id generated by Trident for every transaction |
| ruleSuggestion     | String    | Suggestion given to the transaction                  |
| observationSummary | String    | Observation Summary of every rule                    |
| ratingAdded        | String    | Score of transaction based on Rule                   |
| Rulealiasname      | String    | Alias Name of the Rule                               |
| startTime          | String    | Rule computation start time                          |
| endTime            | String    | Rule computation end time                            |

{% tabs %}
{% tab title="Sample Request" %}
{

"instanceId":"8198",

"channelId":"3DS",

"async":"false",

"details":"true",

"txnSourceType":"3DS",

"acctNumber":"4234563463256899",

"clientId": "20220629204425\_8198\_3DS\_202206171713092164oF0dK9dP", "emailId":"BANGALORE.INDIA@GMAIL.COM",

"partRequest":"true",

"lastDrop" : "true",

"merchantCountryCode": "840",

"sourceCurrencyCode": "999",

"acquirerMerchantID": "7676765432123456789VRDl",

"merchantName": "firstcry",

"custBankAcctNumber":"6543212345678909876",

"purchaseAmount": "542345",

"purchaseDate": "20210409110931",

"mobileNo":"7676767676",

"deviceId": "36S78F6S78FSF78SF7812sw12ws35",

"messageType": "PReq",

"purchaseCurrency" :"356",

"browserAcceptHeader": "text/html, application/xhtml+xml, application/xml", "browserJavaEnabled": true,

"browserLanguage": "English",

"browserColorDepth": "32",

"browserScreenHeight": "768",

"browserScreenWidth": "1200",

"browserTZ": "+530",

"browserUserAgent": "Mozilla/5.0 (Linux; Android 8.0.0; SM-G960F Build/R16NW) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.3202.84 Mobile Safari/537.36", "ip":"3.15.216.82",

"txnType":"OTP\_AUTH",

"browser": "Chrome",

"operatingSystem": "Windows 10 NT",

"merchantCity":"Al Fahahil" ,

"RRN":"214522393819",

"timeStamp" : "20220621123757"

}
{% endtab %}

{% tab title="Success Sample Response" %}
{

"ruleRating": -1000,

"clientId": "20220629204425\_8198\_3DS\_202206171713092164oF0dK9dP", "ruleSuggestion": "DENY",

"observations": \[

{

"ratingAdded": -1000,

"requestId": "1",

"ruleName": "Autoblockingcardiprule",

"ruleId": "RULE::8198::3DS::1656481422761",

"observation": "'purchaseAmount' > '1500' = true ",

"analyzedData": "",

"clientId": "20220629204425\_8198\_3DS\_202206171713092164oF0dK9dP",

"comment": null,

"falseAlarm": null,

"exceptionCase": 0,

"startTime": 1656515669783,

"endTime": 1656515669822,

"mode": 1,

"instanceId": "8198",

"cardPrefix": null,

"ttl": 0,

"timestamp": null,

"exceptionDetail": null,

"methodType": "",

"monthName": "",

"ruleAliasName": "AUTOBLOCKINGCARDIPRULE",

"description": "Autoblockingcardiprule",

"policyDecision": null,

"policyDecisionLevel": null,

"authMode": null, "observationData": {},

"extimatedTimeTaken": 39 },

{

"ratingAdded": 0,

"requestId": "1",

"ruleName": "audit\_rule\_20",

"ruleId": "RULE::8198::3DS::1656493178422",

"observation": "'bin' == '989820' = false 'merchantId' STRING\_NOT\_EQUAL 'hdfc20' = true ", "analyzedData": " subject :hdfc20",

"clientId": "20220629204425\_8198\_3DS\_202206171713092164oF0dK9dP",

"comment": null,

"falseAlarm": null,

"exceptionCase": 0,

"startTime": 1656515669785,

"endTime": 1656515669824,

"mode": 0,

"instanceId": "8198",

"cardPrefix": null,

"ttl": 0,

"timestamp": null,

"exceptionDetail": null,

"methodType": "",

"monthName": "",

"ruleAliasName": "AUDITRULE20",

"description": "audit\_rule\_20",

"policyDecision": null,

"policyDecisionLevel": null,

"authMode": null,

"observationData": {}, "extimatedTimeTaken": 39

}

]

}
{% endtab %}

{% tab title="Fail Sample Response " %}
{

"code": 500,

"message": "There was an error processing your request. It has been logged (ID 8c3e9ca2bd884d22)."

}
{% endtab %}
{% endtabs %}
