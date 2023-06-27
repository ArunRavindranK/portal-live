# Status API

{% swagger method="post" path="" baseUrl="<domain>/wallet/autoTopup/v2/subscriptionStatus" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-PROGRAM-ID" required="true" %}
The Program ID got from the API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}
The Account Number got from the API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" required="true" type="int" %}
country code
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

## Custom response codes

<table><thead><tr><th width="260.5">Response code</th><th>Response description</th></tr></thead><tbody><tr><td>WAL23</td><td>country code should not be zero</td></tr><tr><td>WAL24</td><td>status is inactive</td></tr><tr><td>WAL155</td><td>status is inactive</td></tr><tr><td>WAL156</td><td>please do subscribe autotopup to get autoload benifits</td></tr><tr><td>WAL154</td><td>autotopup status fetched successfully</td></tr></tbody></table>

### Response Details

<table><thead><tr><th width="133">Response Field</th><th>Field Desc</th><th>Data Type</th><th>Length</th></tr></thead><tbody><tr><td>resCode</td><td>response Code of the API</td><td>String</td><td></td></tr><tr><td>resDesc</td><td>response Description of the API</td><td>String</td><td>Variable, 5–8 characters</td></tr></tbody></table>

{% tabs %}
{% tab title="Sample Curl Command" %}
```json
curl --location --request POST '<domain>/wallet/autoTopup/v2/subscriptionStatus' \
\--header 'X-API-TOKEN: replace-with-actual-token'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
--header 'Cookie: JSESSIONID=268743CC4FCDD918A01893968C83A481' \
--data-raw '{
    "countryCode":91
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "countryCode":91
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "WAL154",
    "resDesc": "autotopup status fetched successfully"
}
```
{% endtab %}
{% endtabs %}
