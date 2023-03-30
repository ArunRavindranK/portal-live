---
description: >-
  This API is used to fetch the details that are required for customer KYC
  process i.e) document information.
---

# Fetch KYC Documents API

{% swagger method="get" path="" baseUrl="<domain>/onboarding/user/kyc/fetchKycDocuments/v1 " summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN" required="true" %}
The token got from the

[login API](../../authentication-and-authorization/login-api.md)

or

[Get Token API](../../../common-apis/get-app-token-api.md)
{% endswagger-parameter %}

{% swagger-parameter in="header" required="true" name="X-API-KEY" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":[
      {
         "groupId":"6d1c792b-7f38-498f-a402-d723ac8966a5",
         "docId":"ad689f1c-a9d9-449f-897d-33d78ebedfb5",
         "docName":"PAN"
      },
      {
         "groupId":"6d1c792b-7f38-498f-a402-d723ac8966a5",
         "docId":"f4732993-c909-4128-b29a-9771c9309edc",
         "docName":"Voter ID"
      },
      {
         "groupId":"6d1c792b-7f38-498f-a402-d723ac8966a5",
         "docId":"cbfac263-2883-4f21-8e31-20c2eca78573",
         "docName":"Driving License"
      }
   ]
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
{% tab title="Sample curl request" %}
```json
curl --location --request GET 'http://localhost:8083/onboarding/user/kyc/fetchKycDocuments/v1' \
\--header 'X-API-TOKEN: eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJORVdfVVNFUiIsIlRPS0VOX0VYUElSWSI6NjAsIlJFRkVSRU5DRV9JRCI6IjAyM2VhNjMwLTg1ZDktNDRhNC1hZjRiLWNlOWY3ZTVmZmUyYiIsIkFMTE9XRURfSVBTIjoiKiIsImlzcyI6ImlUSjBUbG0xa1VXb0phWk5HeWFhaUdpY1hLelhNQjVwIiwiZXhwIjoxNjUyODUxNTk2LCJQUk9HUkFNX0lEIjoxMTExLCJpYXQiOjE2NTI4NDc5OTZ9.etMRGGzASs8ZWi6cV70NbFegrsDBtKH2pzNUJ_f5rmm66wNQsKvDTwbCnucRCjEcKLhKPiMnXVAvUabDgeZwmQ'
\--header 'X-API-KEY: MOB-APP-2001'
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
   "resCode":200,
   "resDesc":"SUCCESS",
   "data":[
      {
         "groupId":"6d1c792b-7f38-498f-a402-d723ac8966a5",
         "docId":"ad689f1c-a9d9-449f-897d-33d78ebedfb5",
         "docName":"PAN"
      },
      {
         "groupId":"6d1c792b-7f38-498f-a402-d723ac8966a5",
         "docId":"f4732993-c909-4128-b29a-9771c9309edc",
         "docName":"Voter ID"
      },
      {
         "groupId":"6d1c792b-7f38-498f-a402-d723ac8966a5",
         "docId":"cbfac263-2883-4f21-8e31-20c2eca78573",
         "docName":"Driving License"
      }
   ]
}
```
{% endtab %}
{% endtabs %}
