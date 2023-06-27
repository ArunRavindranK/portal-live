---
description: Load And Pay Controller
---

# Perform Wallet Debit



{% swagger method="post" path="" baseUrl="<domain>/txn/wallet/process/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER " type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="cardFee" type="JSON" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="creditCard" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="debitCard" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="general" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="prepaidCard" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantName" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantTxnId" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="recurringPayment" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="recurringPaymentDetails" type="JSON" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="expiryDate" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="maxAmount" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="minAmount" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="subscriberId" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="subscriberName" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="subscriptionDesc" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="topUpAmount" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="variablePayment" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmt" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnDesc" type="Boolean" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="Boolean" %}

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
```json
curl --location --request POST 'http://localhost:8912/orchestrate/v1/validation' \
--header 'X-PROGRAM-ID: 1111' \
--header 'X-ACCOUNT-NUMBER: 665' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=221E003A0FEB1DFA3D25054F57008EF8' \
--data-raw '{
    "cardFee": {
        "creditCard": 0,
        "debitCard": 0,
        "general": 0,
        "prepaidCard": 0
    },
    "merchantId": 0,
    "merchantName": "Load Money",
    "merchantTxnId": "202208011105327855bP02aI5",
    "recurringPayment": false,
    "txnAmt": 111,
    "txnDesc": "Purchase",
    "txnType": "IAP"
}'
```
{% endtab %}

{% tab title="Request" %}


```json
{
    "cardFee": {
        "creditCard": 0,
        "debitCard": 0,
        "general": 0,
        "prepaidCard": 0
    },
    "merchantId": 0,
    "merchantName": "Load Money",
    "merchantTxnId": "202208011105327855bP02aI5",
    "recurringPayment": false,
    "txnAmt": 111,
    "txnDesc": "Purchase",
    "txnType": "IAP"
}
```
{% endtab %}

{% tab title="Response" %}
```json
// Some code
```
{% endtab %}
{% endtabs %}
