---
description: >-
  Authenticates the user and allow him to proceed. Before calling this API, New
  token has to be generated for the mobile application
---

# Login API

{% swagger method="post" path="" baseUrl="<domain>/onboarding/user/v2/login" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="keyRef" required="true" %}
Key ref is mandatory only for 

[biometric authentication](../../../../version-1/customer-on-boarding/api-specification/biometric-authentication/public-key-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="pin" required="true" %}
If SignInMode is 1 (i.e) Pin based then 4 digit pin should be given. If SignInMode is 2 (i.e) Device based then device id should be encrypted by using

[ public key](../../../../version-1/customer-on-boarding/api-specification/biometric-authentication/public-key-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="signInMode" required="true" %}
signInMode 1 - Pin based mode

signInMode 2 - Device based mode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="token" required="true" %}
The response got from the 

[Get Token API](../../../../../../../../market-place/api-specification/version-1/get-token-api.md)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="authType" required="true" %}
Type of authentication. Since it is from mobile app it should be 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="deviceId" required="true" %}
Device unique id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-ACCOUNT-NUMBER" required="true" %}
100
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "resCode": 200,
    "resDesc": "SUCCESS",
    "data": {
        "msg": "PIN Validated Successfully",
        "token": "eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..qdjwqttibKTehymt.yIZ6bqDiURUB5FOVgrQolK7NxWNfJK5dYd7y4-GYs6fZ90t59_LZ75smtFzfytu1R7TLyWJ-JzCcg1wtFfwkCMXOEX4K_tK1dMmJGoaTBhgAC4DIbtrugursET4w8XpPtK0VioFgkN36n9ik1VFE3pHiElaa7BzFhOK_EFZWccRVN8ca8DK6rruXCr2lO-beDW7dkiBT02m2BKtcP_DaHORm4bxKOjsaLVuiygqMtlOrBUy0MzXqpcIvnw3uGjjkSgJKwQ._j16sEG2vYxYaOm_CJ4LLw",
        "expiry": 1651646789356,
        "simDeviceBindingEnabled": true
    }
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

| Response field          | Field Description                                    | Data type |
| ----------------------- | ---------------------------------------------------- | --------- |
| msg                     | response message                                     | String    |
| token                   | upgraded auth token                                  | String    |
| expiry                  | expiry time of the token                             | long      |
| simDeviceBindingEnabled | sim and device binding completed for one tap payment | Boolean   |

Response Code

| Code   | Description                                                     |
| ------ | --------------------------------------------------------------- |
| ONB014 | Sign in mode mandatory                                          |
| ONB015 | Invalid sign in mode                                            |
| ONB016 | PIN mandatory                                                   |
| ONB017 | Entered PIN is in-correct                                       |
| ONB024 | Device id is mandatory                                          |
| ONB019 | PIN length is mismatch                                          |
| ONB025 | Token mandatory                                                 |
| ONB026 | Login with registered device                                    |
| ONB027 | Pin not set                                                     |
| ONB028 | Pin Locked                                                      |
| ONB029 | Account has been blocked by admin                               |
| ONB004 | Request could not be processed at this time, Please retry again |
| ONB200 | Success                                                         |

{% tabs %}
{% tab title="Sample curl request" %}
```json
curl --location --request POST 'http://localhost:10000/onboarding/user/login/v1' \
--header 'X-API-TOKEN: eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..3wPWIuU643Zkcpz2.BizUuyXgPHzuuFf0w8dhaHV9eFi6IFVTNZrExqtRfIqQJsOYN_C4eNCPU_mdF55czLcWw7lrUHYtIAdGEZMuALer4GFp3pqrTQgACNbRnTSMZJgCVLxCVEpoyMATxN0Bf6U4afeHGbNFmUx5MI_8osFvKIYA6u8thb2OF0SiJBlwuBcNhzhQ_T2rJ5bY10A9xUlU4eUoDaBKjg.-n-LFTVxXNbg9_qh5vy4og'
\--header 'X-API-KEY:MOB-APP-2001'
\--header 'X-ACCOUNT-NUMBER:100'
\--data-raw '{
    "keyRef": "",
    "pin": "1111",
    "signInMode": 1,
    "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..3wPWIuU643Zkcpz2.BizUuyXgPHzuuFf0w8dhaHV9eFi6IFVTNZrExqtRfIqQJsOYN_C4eNCPU_mdF55czLcWw7lrUHYtIAdGEZMuALer4GFp3pqrTQgACNbRnTSMZJgCVLxCVEpoyMATxN0Bf6U4afeHGbNFmUx5MI_8osFvKIYA6u8thb2OF0SiJBlwuBcNhzhQ_T2rJ5bY10A9xUlU4eUoDaBKjg.-n-LFTVxXNbg9_qh5vy4og",
    "authType":"1",
    "deviceId":"anid:lIWuLfmQ7Qmb+Ond5gzXdtMvxyX8EnevuDO/Ggpl7S8=:f3bb"
}'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
    "keyRef": "",
    "pin": "1111",
    "signInMode": 1,
    "token":"eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..3wPWIuU643Zkcpz2.BizUuyXgPHzuuFf0w8dhaHV9eFi6IFVTNZrExqtRfIqQJsOYN_C4eNCPU_mdF55czLcWw7lrUHYtIAdGEZMuALer4GFp3pqrTQgACNbRnTSMZJgCVLxCVEpoyMATxN0Bf6U4afeHGbNFmUx5MI_8osFvKIYA6u8thb2OF0SiJBlwuBcNhzhQ_T2rJ5bY10A9xUlU4eUoDaBKjg.-n-LFTVxXNbg9_qh5vy4og",
    "authType":"1",
    "deviceId":"anid:lIWuLfmQ7Qmb+Ond5gzXdtMvxyX8EnevuDO/Ggpl7S8=:f3bb"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
    "resCode": "ONB200",
    "resDesc": "SUCCESS",
    "data": {
        "msg": "PIN Validated Successfully",
        "token": "eyJlbmMiOiJBMjU2R0NNIiwiYWxnIjoiZGlyIn0..qdjwqttibKTehymt.yIZ6bqDiURUB5FOVgrQolK7NxWNfJK5dYd7y4-GYs6fZ90t59_LZ75smtFzfytu1R7TLyWJ-JzCcg1wtFfwkCMXOEX4K_tK1dMmJGoaTBhgAC4DIbtrugursET4w8XpPtK0VioFgkN36n9ik1VFE3pHiElaa7BzFhOK_EFZWccRVN8ca8DK6rruXCr2lO-beDW7dkiBT02m2BKtcP_DaHORm4bxKOjsaLVuiygqMtlOrBUy0MzXqpcIvnw3uGjjkSgJKwQ._j16sEG2vYxYaOm_CJ4LLw",
        "expiry": 1651646789356,
        "simDeviceBindingEnabled": true
    }
}
```
{% endtab %}
{% endtabs %}
