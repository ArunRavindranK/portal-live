---
description: Merchant Management
---

# Merchant - App and Portal

Merchant Management allows the acquirer to manage the Merchant effectively.

Key Features    &#x20;

1. End to End Support for Merchant Management.
2. Merchant onboarding through UI and File upload option.
3. Merchant App to view the profile, Transaction details.
4. Appropriate Notifications like SMS, Mail, Push, Sticky, Voice alerts in Mobile and Sound box alerts can be enabled.
5. Static and Dynamic QR transaction support.
6. View/download the transaction details at Terminal/Merchant/Admin level for different users.

&#x20;                &#x20;

&#x20;**Merchant Onboarding**

&#x20;  Merchant, Terminal and user details are onboarded in the system using [Merchant](../internal-api-not-to-publish/payment-old/catch-all-no-need-to-publish/merchant-onboarding/), [Merchant Terminal](../internal-api-not-to-publish/merchant-portal-api/merchant-terminal/) and [Merchant user ](../internal-api-not-to-publish/merchant-portal-api/merchant-user/)

<figure><img src="../../../../.gitbook/assets/Merchant Onboarding (1).jpeg" alt=""><figcaption></figcaption></figure>

**Merchant APP Flow**

* Merchant enters the Mobile number and check the onboarding status using [RegistrationStatus ](../wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/registration/check-registration-api.md)API
* Existing Merchants can login to the application using [Renew Token](../wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/common-apis/otp-and-token/renew-token-api.md)(if required) and [Login API](../wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)&#x20;
* For New Merchant, Merchant will be authenticated using [**getToken API**,](https://app.gitbook.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/\~/changes/234/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/common-apis/get-app-token-api)[ **GenerateOTP API** ](https://app.gitbook.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/\~/changes/234/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/common-apis/otp-and-token/generate-otp-api)and **validate OTP API**
* On successful authentication , User will be able to Login using [LOGIN API](../wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md)
* Merchant device details are captured using [Device details API](../wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/registration/save-device-details-api.md),
* Merchant can enable the device lock using [EnableDisableDeviceLock API](../wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/authentication-and-authorization/enable-disable-device-lock-api.md).

**Forgot Pin Flow**

* If Merchant forgot the device pin, he can select the forgot Pin option to reset it
* Merchant will be authenticated using  [**GenerateOTP API** ](https://app.gitbook.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/\~/changes/234/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/common-apis/otp-and-token/generate-otp-api)and [**validate OTP API**](https://app.gitbook.com/o/p6zvZh1r7XYNx0PmyEsS/s/CwdILEPBOX4lLKCKMZGB/\~/changes/234/bankezy/bankezy/bankezy-features/wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/common-apis/otp-and-token/validate-otp-api)
* For Additional Authentication , KYC details(PAN)  is verified using [ValidateKYC](transactions/api-specification/forgot-pin.md) API
* Merchant can reset the device pin/lock using [ResetPin](../wallet/wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/authentication-and-authorization/reset-pin-api.md) API

**Transaction Flow**

* Merchant details is displayed in the merchant profile using[ ](merchant-onboarding/merchant-profile.md)[Merchant Profile](merchant-onboarding/merchant-profile.md) API
* With OneTIme QR , Merchant can enter the transaction amount and remarks and generate Qr using [GenerateQR API](transactions/api-specification/generate-qr.md)
* Merchant can generate static QR as well using [Generate QR API](transactions/api-specification/generate-qr.md)
* Customer can scan the generated QR and perform transaction . On successful credit, merchant will get a transaction status from the CBS through [Callback API](transactions/api-specification/transaction-status-callback.md)
* Application can also check the status of the transaction using [Get transaction status](transactions/api-specification/get-transaction-status.md) API
* Transaction History and detailed status can be retrieved using [Transaction History](transactions/api-specification/transaction-history/merchant-transaction-history.md) and [transaction detail API](transactions/api-specification/transaction-history/merchant-transaction-history.md)
* Based on the Notification setting configured using [Enable Notification API](transactions/api-specification/notification/enable-notification.md), SMS, Email , Push and voice alerts will be sent.



&#x20;

