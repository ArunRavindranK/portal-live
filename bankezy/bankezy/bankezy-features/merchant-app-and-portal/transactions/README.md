---
description: >-
  Merchant can perform transactions and view the transaction details performed
  for the time period.
---

# Transactions

Merchant will have options to generate static and dynamic QR in the app dashboard. Generated QR can be shared with anyone or downloaded in the mobile or shown directly to customer. Dynamic QR validity can be configured by the Bank admin. Both static and dynamic QR can be signed QR if bank can expose the sign QR API. Each QR will contain references of merchant id and terminal id. Whenever a transaction happens in a static QR, all users under the terminal will get the alerts as per their configuration. Whenever a transaction happens in a dynamic QR, user who displayed the QR, will get the alert after transaction basis their configuration.

&#x20;

API Specification
