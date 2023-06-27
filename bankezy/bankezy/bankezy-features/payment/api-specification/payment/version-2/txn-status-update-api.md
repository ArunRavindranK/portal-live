---
description: This API used to update the txn status in case of failures like user abort
---

# Txn Status Update API

{% swagger method="get" path="" baseUrl="/payments/txn/status/update" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnStatus" type="String" required="true" %}
status of the transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wibmoTxnId" type="String" required="true" %}
transactionId to update the status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="comment" type="String" required="true" %}
transaction stauts update comments
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merId" type="String" required="true" %}
merchantId for the requested transaction
{% endswagger-parameter %}

{% swagger-parameter in="body" name="loginDone" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="breadCrumb" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="abortStatusCode" type="String" required="true" %}
status code in case of aborting the transaction.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="abortMessage" required="true" %}
abort message in case of aborting the transaction
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Curl Command" %}
```
curl --location --request POST 'http://localhost:2442/payments/txn/status/update' \
--header 'X-API-KEY: MOB-APP-1111' \
--header 'X-API-TOKEN: Token' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=8CEC7C43996D57C3E7A7BE123530348F' \
--data-raw '{
"txnStatus" : "ABORTED",
"wibmoTxnId" : "202331050223456",
"comment" : "ABORT COMMENTS",
"merId" : "123456fg5",
"breadCrumb" : "/payment",
"abortStatusCode" : "250",
"abortMessage" : "ABORT MESSAGE"
}'
```
{% endtab %}

{% tab title="Sample Request" %}
```json
{
"txnStatus" : "ABORTED",
"wibmoTxnId" : "202331050223456",
"comment" : "ABORT COMMENTS",
"merId" : "123456fg5",
"breadCrumb" : "/payment",
"abortStatusCode" : "250",
"abortMessage" : "ABORT MESSAGE"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```
{
    "resCode": "200",
    "resDesc": "SUCCESS",
    "data": null
}
```
{% endtab %}
{% endtabs %}
