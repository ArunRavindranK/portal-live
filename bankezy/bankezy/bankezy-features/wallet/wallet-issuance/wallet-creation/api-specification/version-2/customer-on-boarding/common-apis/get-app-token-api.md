---
description: >-
  This API is used for  Diffie-Helman key exchange between the client and the
  server along with JWT token generation.
---

# Get App Token API

{% swagger method="post" path="" baseUrl="/token-service/new/v2/token" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="apiKey" required="true" %}
Will  be shared offline
{% endswagger-parameter %}

{% swagger-parameter in="body" name="publicKey" required="true" %}
Key  generated at client  end
{% endswagger-parameter %}

{% swagger-parameter in="body" name="secret" required="true" %}
Will  be shared offline
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
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

## Response Details

| Response field  | Field description                                  | Data Type |
| --------------- | -------------------------------------------------- | --------- |
| resCode         | response code                                      | Integer   |
| resDesc         | response description                               | String    |
| token           | JWT token                                          | Sting     |
| expiry          | token expiry time                                  | Long      |
| serverPublicKey | public key for doing encryption on request payload | String    |

#### Response Code

| Response Code | Response Description                           |
| ------------- | ---------------------------------------------- |
| TOK200        | Success                                        |
| TOK002        | Invalid API Key Passed                         |
| TOK004        | Your credentials not allowed to generate token |
| TOK003        | Failure                                        |

{% tabs %}
{% tab title="Sample Curl Request" %}
{% code overflow="wrap" %}
```json
curl --location --request POST '<domain>/token-service/new/v2/token'
--header 'Content-Type: text/plain'
--data-raw '{ "apiKey": "MOB-APP", "publicKey": "eyJrdHkiOiJFQyIsImNydiI6IlAtMjU2IiwieCI6ImxCSGpLNHVaNjVMTVdZVXZKOTY4TTFxWGkzN21BSVRIWlhvSUk5c0xQYUUiLCJ5IjoiUmQtbmg0Rlk3ZnFLUTU0bHBOUVBMa2taVGpWUGlab25LaVRFOUQ0aXNWTSJ9", "secret": "TEST123" }'
```
{% endcode %}
{% endtab %}

{% tab title="Request sample" %}
```json
{
   "apiKey":"ABC",
   "publicKey":"eyJrdHkiOiJFQyIsImNydiI6IlAtMjU2IiwieCI6IkhnTTdrSEhRSGYxRmtmT0UwSFNyUkNUTkpIUFNRQlViSEdEM0tjUEw1ckEiLCJ5IjoicmljOS1uOUpRUDJjZjFIVEVNZjA2",
   "secret":"BankeZy123"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 100,
    "resDesc": "Success",
    "token": "eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..7f8V7IrXBnXYdZXi.VHTaVKnfSyiFM1ZUQyp5-lGTpVtXhH6RRyzSTBP4WX_iNCvPTvTe750q3j_ufIiNqFRluLsxFbHUcYzR4b_NQlMgolKcOM-LsYVT81jwxcBS9GhLC2XOOuOIJHux-ozr_FUMfN8IH5vFveIP54_aBEOsy-_8FaGUuBHCIrY0shfRQptUN53f0HahwqMlSufErS8PACRrHe4h.hiI1_9wyDa3BH_XxiCXccA",
    "expiry": 1651216460918,
    "serverPublicKey": "eyJrdHkiOiJFQyIsImNydiI6IlAtMjU2IiwieCI6IjZad2phdHZSSW9ZTjVFRWVIZTdmUXJPOGVGQzRsRmJMSmlmalB4RFF0S0UiLCJ5IjoiMjhZcE9meWhoTkpNa1hpdEg4OU14dm4xRGJWZmJoVS1wMVVLdjFjcUpCOCJ9"
}
```
{% endtab %}
{% endtabs %}
