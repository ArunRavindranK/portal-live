---
description: Wibmo APIs are completely RESTful and all our responses are returned in JSON.
---

# API Reference Guide

## Onboarding

Please get in touch with your Wibmo representative to onboard you. Once onboarded you will get:

* "x-api-key" will be issued at the time of onboarding.
* InstanceID will be issued at the time of onboarding.
* ChannelID based on the channel selected (eg. 3DS or POS) will be issued.
* API URL (You need to include this before each API endpoint to make API calls.)

## API Gateway URL

The Wibmo token hub API Gateway URL will be shared with you by your Wibmo representative. You need to include this before each API endpoint to make API calls.

{% hint style="warning" %}
**Recommendation**\
While sending API requests to Wibmo servers, it is recommended to honor the TTL of the entries and not cache the DNS aggressively at your end. This is applicable when you are not using Wibmo SDKs. However, if you are using Wibmo SDKs, be informed that our SDKs can handle DNS caching and honor the TTLs that are set in the records.
{% endhint %}

## API Authentication

All Wibmo APIs are authenticated using `Key Auth`. Key auth requires the following:

* x-api-key

Key auth expects an x-api-key header for each request

{% hint style="warning" %}
**Watch Out!**\
Alternatively you can also send the x-api-key as a URL parameter, but pls make sure that is case sensitive.
{% endhint %}

{% hint style="danger" %}
**Recommended**

* Use x-api-key in header as the most common and secure way to call apis.
* If you need to share links to browser clients, use `the key in query`. Note that query parameter requests can appear within application logs and URL browser bars, which expose the API key.
{% endhint %}

## Generate API Keys

Please get in touch with your respective Wibmo representative, to get the API Keys for integration.
