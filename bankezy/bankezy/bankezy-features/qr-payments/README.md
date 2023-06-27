---
description: Universal QR
---

# QR Payments

Universal QR Payments can be used for performing different types of QR transactions.

Universal QR Payments Key Features

* Enables the QR app to scan different types of QR code and process your payment. Supports both static & dynamic QR code payment.
* Enables the application to support processing of multiple QR formats including Bharat QR, UPI Qr and PHQR. QR Payments related to transactions like P2P(Person to person), P2M(Person to Merchant) and P2B(Person to Biller) can be configured.
* Seamlessly integrated with Bank Partners/Payment Gateway & Merchants to support P2P,P2M,P2B transactions.Payments for QR transactions are supported through open banking API standards.
* Specifications related to the QR format is configured and validations with respect to length, expected value, required for the transaction type can be performed through configuration.

Below diagram explain the QR Payments transaction flow

<figure><img src="../../../../.gitbook/assets/QR Payments Transaction Flow.png" alt=""><figcaption></figcaption></figure>

1. QR Payments App users will be onboarded using BankeZy onboarding /onboarding/user/token API.
2. User Login to app and initiate Scan & Pay QR transactions using [Parse QR API](api-specification/parse-qr.md) to parse the raw QR data. This step is optional in case if app has the logic for QR parsing.
3. Merchant specific fee configured can be retrieved using [Fetch Fees API](api-specification/fetch-fees-api.md) if the QR does not contain any additional fee.
4. Post receiving QR Parse response, App will initiate the [Fetch Accounts API](account-services/api-specification/fetch-accounts-api.md) to retrieve user linked bank accounts.
5. Consent Api Initiates transaction and validates user consumption and generates OTP to the user. Post Successful Completion of user entering Transaction amount & description, App initiates the transaction consent request using [Payment Consent API](api-specification/payment-consent-api.md) .
6. Post completion of entering OTP and triggering Confirm & Pay by the User, App invokes [Process Payments API](api-specification/customer-debit-host.md) to validate OTP  and processing of payment transaction request.&#x20;
7. QR Payments App User will be able to receive money via QR transaction using[ **Receive Money API**](api-specification/customer-credit-gateway.md)

#### QR Payments Account Management Service

Account service features enables to partner with CBS provider and manage user accounts and perform payment transactions such as debit, credit and refund. Apis are supported through open banking API standards.

Following are the Apis related to account service

1. To Update a primary account which is used as default selected account for QR payments, [Primary Accounts API](account-services/api-specification/primary-accounts-api.md) to be used.
2. To Manage/Fetch user linked accounts for QR payments [Fetch Accounts API](account-services/api-specification/fetch-accounts-api.md) to be used.
3. To amend list of user linked accounts used for QR payments, [Linked Accounts API](account-services/api-specification/linkedaccounts-api.md) to be used.

All the request and response parameters are encrypted.
