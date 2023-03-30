---
description: >-
  This page explains about the steps to be taken by the partner in consuming the
  BankEzy API securely.
---

# API Reference Guide

## **API Authentication**

***

**X-API-KEY header to be added**

For any api to consume X-API-KEY header parameter to be added

## **Content-Type header should be added**

Content type header should have the value as text/plain

## Payload encryption

JSON payload should be converted into string and encrypt with payloadSecret given by BankEzy during onboarding process.

Once response is received payload should be decrypted using the same payloadSecretKey.

All REST APIs in BankEzy are required end to end payload encryption. Payload secret key is either derived randomly with key-exchange or static key during the Onboarding.

Here we provide the logic to encrypt and decrypt using the java language.

**Prerequisites: -**

Include the crypto-service-X.jar provided by the Wibmo into your java projects. Also add below maven/gradle dependencies into your projects.

implementation group: 'com.nimbusds', name: 'nimbus-jose-jwt', version: '9.7

implementation group: 'org.bouncycastle', name: 'bcprov-jdk15on', version: '1.64'

Once prerequisites are done, please follow below while calling api:-

1. Create payload java object
2. Use ObjectMapper or similar class to convert payload into string value
3. Create the com.wibmo.dfs.crypto.PayLoadEncryptionService object (Thread safe)
4. Call encrypts method of object created above by passing jsonString and payloadSecretKey
5. As a return value will get String and pass the string as payload for API
