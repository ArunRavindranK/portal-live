# MerchantTransactionHistory

{% swagger method="post" path="/txnHistory/v1/merchanttxn" baseUrl="<domain>" summary="Merchant Txn history" %}
{% swagger-description %}
This is to fetch the merchant txn history from start date to end date.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fromDate" required="true" %}
fromDate to fetch merchant transaction history
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP1-1114
{% endswagger-parameter %}

{% swagger-parameter in="body" name="toDate" required="true" %}
toDate to fetch merchant transaction history
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnType" type="List<String>" %}
transaction type

eg: PAY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnStatus" type="List<String>" %}
transaction status

eg: SUCCESS , FAILED etc..
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnId" %}
transaction id
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

{% tabs %}
{% tab title="Sample curl command" %}
```
curl --location --request POST 'https://user4.pcdev.enstage-sas.com/kong/txnHistory/v1/merchanttxn' \
--header 'X-API-TOKEN: token' \
--header 'X-API-KEY: MOB-APP' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fromDate":"2022-12-05 00:00:00",
    "toDate":"2022-12-11 00:00:00"
}'
```
{% endtab %}

{% tab title="Request sample" %}

{% endtab %}

{% tab title="Response sample" %}

{% endtab %}
{% endtabs %}
