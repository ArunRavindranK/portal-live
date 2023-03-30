---
description: >-
  After the transaction completion the client sends the transaction status to
  Trident by consuming the ‘UpdateTxnStatus’ API
---

# Update Request API

{% swagger method="post" path="/updateTxnStatus" baseUrl="http://trident.pc.enstage-sas.com/trident/analyse/POS" summary="Update Request" %}
{% swagger-description %}
Below are the specifications for consuming REST API. Request Data and Response are mentioned below along with sample values
{% endswagger-description %}

{% swagger-parameter in="body" name="clientId" required="true" %}
It is the unique identifier created by Trident for every Transaction, which is same as from V-Request.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-api-key" required="false" %}
To be shared at the time of onboarding
{% endswagger-parameter %}

{% swagger-parameter in="body" name="finalStatus" required="true" %}
3 digit numeric code based w.r.t transaction channel.

Final status of transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="action" required="false" %}
Action taken by ACS
{% endswagger-parameter %}

{% swagger-parameter in="body" name="challengeType" required="false" %}
Authentication type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="reason" required="false" %}
3 digits numeric code w.r.t transaction channel

Reason for failure of Transaction
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

{% tabs %}
{% tab title="Sample Request" %}
{

"clientId": "20220629204425\_8198\_3DS\_202206171713092164oF0dK9dP", "finalStatus":"100",

"action":"001",

"challengeType" :"002",

"reason":"014"

}
{% endtab %}

{% tab title="Sample Response" %}
{ "async": "true", "ack": "true", "NodeId": "192.168.29.99::8085" }
{% endtab %}
{% endtabs %}
