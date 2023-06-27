---
description: This API helps to process user refund initiated by the Merchant.
---

# Refund

&#x20;&#x20;

{% swagger method="post" path="/lending/v1/refund" baseUrl="<domain>" summary="Initiate the customer Refund" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
value will be pre-shared with consumer
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" type="String" required="true" %}
The token got from the 

[Get Token API](../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="Amount" type="Number" required="true" %}
Transaction Amount with max 2 decimals
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Reason" type="Int" required="true" %}
Reason for Refund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Action" type="int" required="true" %}
"REFUND"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="transaction Id" %}
Transaction Identifier
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
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

{% swagger-response status="404: Not Found" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

### Custom Response Codes

| Response Code | Response Description                                  |
| ------------- | ----------------------------------------------------- |
| LND025        | INVALID AMOUNT                                        |
| LND030        | INVALID TXNID                                         |
| LND031        | INVALID ACTION                                        |
| LND032        | INVALID REASON                                        |
| LND037        | Refund already initiated for this transaction.        |
| LND026        | INVALID MERCHANT                                      |
| LND200        | SUCCESS                                               |
| LND009        | There seems to be a technical issue. Try again later. |

### Response Details

| Response Body | Data Type | Field Description            |
| ------------- | --------- | ---------------------------- |
| resCode       | String    | Response Code                |
| resDesc       | String    | Response Description         |
| txnRefNum     | String    | Transaction Reference Number |

{% tabs %}
{% tab title="Sample Curl Request" %}
<pre><code>curl --location 'https://user4.pcdev.enstage-sas.com/kong/lending/v1/refund' --header 'X-API-KEY: MOB-APP' --header 'X-API-TOKEN: Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJORVdfVVNFUiIsIlRPS0VOX0VYUElSWSI6OTAwLCJSRUZFUkVOQ0VfSUQiOiI2OGQ4NDg5Zi1hOWI2LTQzMjYtYjMzNi0zYWZlNGRlYmFlYzkiLCJhY2NlcHQtbGFuZ3VhZ2UiOiJlbiIsIkFMTE9XRURfSVBTIjoiKiIsImlzcyI6ImlUSjBUbG0xa1VXb0phWk5HeWFhaUdpY1hLelhNQjVwIiwiZXhwIjoxNjgxOTQzNzM0LCJQUk9HUkFNX0lEIjoxMTExLCJpYXQiOjE2ODE4ODk3MzR9.eU7_PGfGLZTPL4grC697tDYlTAoGh6FTqrZax3ivGYMNKkOFK2nGIv8_Wwm6FhnCp6OXcl8sdNFszOJD_O1TSg' --header 'X-ACCOUNT-NUMBER: 1234568188' --header 'Content-Type: application/json' --data '{

 

"amount": 15000,
"reason" : "Size Issue"    ,
"action": "REFUND",
"txnId": "202303160939566038kC88sB2"
}'
<strong>
</strong></code></pre>
{% endtab %}

{% tab title="Sample Request " %}
curl --location '[https://user4.pcdev.enstage-sas.com/kong/lending/v1/refund'](https://user4.pcdev.enstage-sas.com/kong/lending/v1/refund') --header 'X-API-KEY: MOB-APP' --header 'X-API-TOKEN: Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJORVdfVVNFUiIsIlRPS0VOX0VYUElSWSI6OTAwLCJSRUZFUkVOQ0VfSUQiOiI2OGQ4NDg5Zi1hOWI2LTQzMjYtYjMzNi0zYWZlNGRlYmFlYzkiLCJhY2NlcHQtbGFuZ3VhZ2UiOiJlbiIsIkFMTE9XRURfSVBTIjoiKiIsImlzcyI6ImlUSjBUbG0xa1VXb0phWk5HeWFhaUdpY1hLelhNQjVwIiwiZXhwIjoxNjgxOTQzNzM0LCJQUk9HUkFNX0lEIjoxMTExLCJpYXQiOjE2ODE4ODk3MzR9.eU7\_PGfGLZTPL4grC697tDYlTAoGh6FTqrZax3ivGYMNKkOFK2nGIv8\_Wwm6FhnCp6OXcl8sdNFszOJD\_O1TSg' --header 'X-ACCOUNT-NUMBER: 1234568188' --header 'Content-Type: application/json' --data '{

&#x20;

"amount": 15000,\
"reason" : "Size Issue"    ,\
"action": "REFUND",\
"txnId": "202303160939566038kC88sB2"\
}'
{% endtab %}

{% tab title="Sample Response" %}
{  "resCode": "LND\_2000", &#x20;

&#x20;  "resDesc": "SUCCESS",  &#x20;

&#x20; "data": {    &#x20;

&#x20;   "txnRefNum": "202301061100489202eT19cI0"&#x20;

&#x20;       }&#x20;

}
{% endtab %}
{% endtabs %}
