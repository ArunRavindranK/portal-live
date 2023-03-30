---
description: Wibmo APIs are completely RESTful and all our responses are returned in JSON.
---

# API Reference Guide

## API Gateway URL

The Wibmo token hub API Gateway URL will be shared with you by your Wibmo representative. You need to include this before each API endpoint to make API calls.

{% hint style="warning" %}
**Recommendation**\
While sending API requests to Wibmo servers, it is recommended to honor the TTL of the entries and not cache the DNS aggressively at your end. This is applicable when you are not using Wibmo SDKs. However, if you are using Wibmo SDKs, be informed that our SDKs can handle DNS caching and honor the TTLs that are set in the records.
{% endhint %}

## API Authentication

All Wibmo APIs are authenticated using `Key Auth`. Key auth requires the following:

* `[YOUR_KEY_SECRET]`

Key auth expects an `clientApiKey` header for each request

clientApiKey`:YOUR_KEY_SECRET`.

{% hint style="warning" %}
**Watch Out!**\
Alternatively you can also send the clientApiKey as a URL parameter, but pls make sure that is case sensitive.
{% endhint %}

{% hint style="danger" %}
**Recommended**

* Use clientApiKey in header as the most common and secure way to call apis.
* If you need to share links to browser clients, use `the key in query`. Note that query parameter requests can appear within application logs and URL browser bars, which expose the API key.
{% endhint %}

## Generate API Keys

Please get in touch with your respective Wibmo representative, to get the API Keys for integration.
