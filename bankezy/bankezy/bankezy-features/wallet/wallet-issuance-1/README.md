# Wallet Issuance

This section covers the list of API's to create wallet.

KYC is mandatory to create a wallet.

KYC to create a wallet can be of:&#x20;

* Bank Customer KYC
* Non-Bank Customer KYC - MIN KYC
* Non-Bank Customer KYC - EKYC&#x20;

<figure><img src="../../../../../.gitbook/assets/Wallet - SendMoney Design - KYC.png" alt=""><figcaption><p>KYC Process</p></figcaption></figure>

## User Identification

* To identify the user type whether the use is a Bank Customer or a Non Bank Customer refer [Fetch Details API](../wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/authentication-and-authorization/fetch-details-api.md)

## Bank Customer KYC

* To validate the Bank Customer KYC refer [Verify Bank KYC API](../wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/bank-customer-kyc-process/verify-bank-kyc-api.md)
* To fetch the cards linked with Bank account refer [Fetch Bank Cards API](../wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/bank-customer-kyc-process/fetch-bank-linked-cards-api.md)

## Non - Bank Customer KYC&#x20;

There 2 ways to complete non - bank customer KYC

1. OVD (Officially Valid Documents)
2. Aadhar KYC

### OVD

* To fetch the available OVDs refer [Fetch Kyc Documents API](../wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/non-bank-customer-kyc-process/min-kyc-process/fetch-client-rules-api.md)
* To validate the entered OVD number by user refer [Update KYC Details API](../wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/non-bank-customer-kyc-process/min-kyc-process/update-kyc-details-api.md)

### Aadhar KYC / EKYC

* To validate the aadhar number entered by user refer [Verify Aadhar API](../wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/non-bank-customer-kyc-process/ekyc-process/verify-aadhar-api.md)
* To validate the OTP number received for aadhar validation refer [Verify Aadhar OTP API](../wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/non-bank-customer-kyc-process/ekyc-process/verify-aadhaar-otp-api.md)
* To confirm the profile details fetched from UIDAI refer [Verify EKYC API](../wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/non-bank-customer-kyc-process/ekyc-process/verify-ekyc-api.md)
* To resend OTP in case of expiry refer Verify [Resend OTP API](../wallet-issuance/wallet-creation/api-specification/version-2/customer-on-boarding/api-specification/non-bank-customer-kyc-process/ekyc-process/resend-otp-api.md)











