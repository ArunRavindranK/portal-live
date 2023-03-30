---
description: >-
  This page explains about the steps to be taken by the partner in consuming the
  BankEzy API securely.
---

# API Reference Guide

## **API Authentication**

****

**X-API-KEY header to be added**&#x20;

For any api to consume X-API-KEY header parameter to be added&#x20;

## **Content-Type header should be added**&#x20;

&#x20;Content type header should have the value as text/plain&#x20;

## &#x20;Payload encryption &#x20;

JSON payload should be converted into string and encrypt with payloadSecret given by BankEzy during onboarding process.&#x20;

&#x20;Once response is received payload should be decrypted using the same payloadSecretKey.&#x20;

All REST APIs in BankEzy are required end to end payload encryption. Payload secret key is either derived randomly with key-exchange or static key during the Onboarding.&#x20;

Here we provide the logic to encrypt and decrypt using the java language.&#x20;

**Prerequisites: -**&#x20;

&#x20;Include the crypto-service-X.jar provided by the Wibmo into your java projects. Also add below maven/gradle dependencies into your projects.&#x20;

&#x20;implementation group: 'com.nimbusds', name: 'nimbus-jose-jwt', version: '9.7&#x20;

implementation group: 'org.bouncycastle', name: 'bcprov-jdk15on', version: '1.64'&#x20;

&#x20;Once prerequisites are done, please follow below while calling api:-&#x20;

1. Create payload java object &#x20;
2. Use ObjectMapper or similar class to convert payload into string value&#x20;
3. Create the com.wibmo.dfs.crypto.PayLoadEncryptionService  object (Thread safe)&#x20;
4. Call encrypts method of object created above by passing jsonString and payloadSecretKey &#x20;
5. As a return value will get String and pass the string as payload for API&#x20;

&#x20;
