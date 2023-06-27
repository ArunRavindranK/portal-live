---
description: This API is helps to renew the token expiry time.
---

# Renew Token API



{% swagger method="post" path="/onboarding/token/renewToken/v1" baseUrl="<domain>" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the 

[login API](../../api-specification/authentication-and-authorization/login-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" required="true" %}
api token needs to be passed
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "loginId": 7073,
        "accountNumber": "665",
        "token": "eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..rFrDlC5vtCD6LrRa.vazS8DZ_RlF1c7pzoynsvzYhkhaE-POnNbh9AG0mAmMgZ1NfF-u8nHhO47Qm2M-CKHXIwzDlfg0SmJg7ADXLzzSsFocYNLWLAHTj5_j7Eq_kciJRCiv_4DjgB3wJbs7sSDOVacaTG9xAVwGm6mQCXvJskpiN3N1y0fK6xK_i-BaVCFA6A5eJlUI8TJ45L-S950TrTiHPDzxyhmwE1ZNM6n9VAIx0qNEj0PVppk0vvXoPge4A-gQoUIYW7k6e1LVYCuueaPE.PP9vWivGNUQ9bMO_d0NfcQ",
        "expiryDate": 1651497083574
    }
}
```
{% endswagger-response %}
{% endswagger %}

## Response Details

| Response field | Field description   | Data type |
| -------------- | ------------------- | --------- |
| loginId        | user login id       | Integer   |
| accountNumber  | user account number | String    |
| token          | JWT token           | String    |
| expiryDate     | expiry of the token | Long      |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:8083/onboarding/token/renewToken/v1' \
\--header 'X-API-TOKEN: token'
\--header 'X-API-KEY:MOB-APP-2001'
\--data-raw '{
   "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..HA9RvVYEDISlQ4ov.uLPQ-bIjk-RahllHaOPDypZo9CG8z7rV-RSqTAQWlOOQprctqsUTCtoZRDeoF0qyi0PKOg-67X2r4U-6JWAi4i6LdGDEBbWyFT86xYqWopPXvM-US4YC2J6qvi3O4oPhFM8TXwrhyQtAS2_HqDZkuo8aXLWzOEMvL42vHqA8v4eoN0970eRLtCrtdUH5iWEkDX8tkHeLFKvHTwYVXjS-rt8zvV2eztP3pXGsM-29gaKhOkaSMBM__uPzG9jF5b04b87Hw78.3cbZqKJmuhaFGibPcRa50A"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json5
{
   "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..HA9RvVYEDISlQ4ov.uLPQ-bIjk-RahllHaOPDypZo9CG8z7rV-RSqTAQWlOOQprctqsUTCtoZRDeoF0qyi0PKOg-67X2r4U-6JWAi4i6LdGDEBbWyFT86xYqWopPXvM-US4YC2J6qvi3O4oPhFM8TXwrhyQtAS2_HqDZkuo8aXLWzOEMvL42vHqA8v4eoN0970eRLtCrtdUH5iWEkDX8tkHeLFKvHTwYVXjS-rt8zvV2eztP3pXGsM-29gaKhOkaSMBM__uPzG9jF5b04b87Hw78.3cbZqKJmuhaFGibPcRa50A"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "loginId": 7073,
        "accountNumber": "665",
        "token": "eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..rFrDlC5vtCD6LrRa.vazS8DZ_RlF1c7pzoynsvzYhkhaE-POnNbh9AG0mAmMgZ1NfF-u8nHhO47Qm2M-CKHXIwzDlfg0SmJg7ADXLzzSsFocYNLWLAHTj5_j7Eq_kciJRCiv_4DjgB3wJbs7sSDOVacaTG9xAVwGm6mQCXvJskpiN3N1y0fK6xK_i-BaVCFA6A5eJlUI8TJ45L-S950TrTiHPDzxyhmwE1ZNM6n9VAIx0qNEj0PVppk0vvXoPge4A-gQoUIYW7k6e1LVYCuueaPE.PP9vWivGNUQ9bMO_d0NfcQ",
        "expiryDate": 1651497083574
    }
}
```
{% endtab %}
{% endtabs %}
