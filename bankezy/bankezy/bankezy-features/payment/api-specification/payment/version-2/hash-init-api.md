---
description: This API used to calculate hash for the required keys.
---

# Hash init API

{% swagger method="post" path="" baseUrl="/payments/v2/hash/init" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="requestFor" type="String" %}
Hash generation requested for
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="String" %}
email of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantId" type="String" required="true" %}
merchant Id to generate the hashes
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merchantTxnId" type="String" required="true" %}
txnId 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="firstName" type="String" required="false" %}
firstname of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnAmt" type="long" required="true" %}
txn amount for transactions
{% endswagger-parameter %}

{% swagger-parameter in="body" name="udfParams" type="Map" %}
udf params if we have any for the transactions
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="String" %}
User mobile number 
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

## Custom response codes

| Code   | Description          |
| ------ | -------------------- |
| PMT001 | Execution Failure    |
| PMT200 | SUCCESS              |
| PMT004 | Invalid merchant Id  |
| PMT005 | Invalid paymentTxnId |



{% tabs %}
{% tab title="Curl Command" %}


```json

curl --location --request POST 'http://localhost:2442/payments//v2/hash/init' \
--header 'X-API-KEY: MOB-APP-1111' \
--header 'X-API-TOKEN: Token' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=8CEC7C43996D57C3E7A7BE123530348F' \
--data-raw '{
"merchantId" : 81516123,
"email" : "manoharakumar@gmail.com",
"txnAmt" : 1234,
"firstName" : "venkat",
"requestFor" : "payments",
"merchantTxnId" : "123456789"
}'
```
{% endtab %}

{% tab title="Sample Request" %}


```json
{
    "merchantId": 81516123,
    "email": "manoharakumar@gmail.com",
    "txnAmt": 1234,
    "firstName": "venkat",
    "requestFor": "payments",
    "merchantTxnId": "123456789"
}
```
{% endtab %}

{% tab title="Sample Response" %}
```
{
    "resCode": "200",
    "resDesc": "SUCCESS",
    "data": {
    "paymentHash" : "dasdsadsaf23asfdf3vsvds3543533vsvdssdsdsfdsfsfsddsnkv",
    "paymentDetailHash" : "ghsdsadsaf23asfdf3vsvds3543533vsvdssdsdsfdsfsfsddsnkv",
    "vasHash" : "43rgdsadsaf23asfdf3vsvds3543533vsvdssdsdsfdsfsfsddsnkv",
    "getCardHash" : "3456sfdsadsaf23asfdf3vsvds3543533vsvdssdsdsfdsfsfsddsnkv",
    "saveCardHash" : "12456ghdsadsaf23asfdf3vsvds3543533vsvdssdsdsfdsfsfsddsnkv",
    "checkoutDetailsHash" : "d3425asdsadsaf23asfdf3vsvds3543533vsvdssdsdsfdsfsfsddsnkv",
    "editCardHash" : "da2345sdsadsdaf23asfdf3vsvds3543533vsvdssdsdsfdsfsfsddsnkv",
    "deleteCardHash" : "d34454asdsadsaf23asfdf3vsvds3543533vsvdssdsdsfdsfsfsddsnkv",
    "binInfoHash" : "d345568sdsadsaf23asfdf3vsvds3543533vsvdssdsdsfdsfsfsddsnkv"
    }
}
```
{% endtab %}
{% endtabs %}
