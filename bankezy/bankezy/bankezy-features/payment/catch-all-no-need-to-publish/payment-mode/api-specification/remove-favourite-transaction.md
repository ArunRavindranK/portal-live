---
description: This api helps to remove the favourite transaction from database
---

# Remove favourite transaction

{% swagger method="get" path="" baseUrl="<domain>/merchant/user/v1/remove/favourite/payment" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
tenant id 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="encCardNumber" required="true" %}
encrypted cardnumber. Encryption process is based on HSM 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accountNumber" type="int" required="true" %}
Unique identification for user
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
{% endswagger %}

{% tabs %}
{% tab title="Sample Curl Command" %}
```json5
curl --location --request POST 'http://localhost:2442/merchant/user/v1/remove/favourite/payment' \
--header 'X-PROGRAM-ID: 1111' \
--header 'Content-Type: application/json' \
--header 'Cookie: JSESSIONID=1EFD299E213DEE8847A52413CD0FB47E' \
--data-raw '{
    "encCardNumber":"snUnDWrMCmfSsbkom2TwQw3IuMto9apr",
    "accountNumber":665
}'
```
{% endtab %}

{% tab title="Request" %}
```json
{
    "encCardNumber":"snUnDWrMCmfSsbkom2TwQw3IuMto9apr",
    "accountNumber":665
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
    "resCode": 200,
    "resDesc": "Removed card details successfully"
}
```
{% endtab %}
{% endtabs %}
