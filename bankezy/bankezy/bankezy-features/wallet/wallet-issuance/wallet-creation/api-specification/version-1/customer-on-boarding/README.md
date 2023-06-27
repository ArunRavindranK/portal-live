# Account Creation and Onboarding

To provide a smooth journey during the process of onboarding a customer, we provide various customisable registration flow to meet the business needs in a secure and convenient way.  This module covers both the mandatory and customisable steps involved during the registration process.

<figure><img src="../../../../../../../../../.gitbook/assets/BankEzy Flows - Page 6.png" alt=""><figcaption><p>Customer onboarding process</p></figcaption></figure>

### Mandatory Registration Steps

1. Generate a KeyPair&#x20;
2. Share the public key to the server to get the token and server's public key using [Get App Token API](common-apis/get-app-token-api.md)
3. Generate a secret for Payload encryption and decryption.
4. Provide a unique customer ID to check if the user is registered in BankeZy or not using [Check Registration API](api-specification/registration/check-registration-api.md)
5. Authenticate the user to proceed with Registration using [Generate OTP](common-apis/otp-and-token/generate-otp-api.md) and [Validate OTP API](common-apis/otp-and-token/validate-otp-api.md)
6. Check the user type whether bank / non bank customer and KYC / non KYC / Min KYC customer using [Fetch Details API](api-specification/authentication-and-authorization/fetch-details-api.md) in order to proceed with customisable registration step as specified below
7. User Authentication supports both PIN and device based Authentication.
8. To Support device based authentication, as an additional security check, need to call the [Public Key API,](api-specification/biometric-authentication/public-key-api.md) encrypt  the unique device ID using the public key fetched from the server and should be passed as PIN in the below step.
9. Complete the registration using [Save Credentials API](api-specification/registration/save-credentials-api.md)

### Customisable Registration Steps

Below are the key flows that can be customised based on the business needs

1. Upfront educating the customer and taking the consent for the mandatory permissions required for the application using [Save Device Details API.](api-specification/registration/save-device-details-api.md)
2. If the user is Bank customer the full KYC status of the customer shall be verified using API [Verify Bank KYC API](api-specification/bank-customer-kyc-process/verify-bank-kyc-api.md)
3. Fetching all types of cards linked to the user's bank account using [Fetch Bank Linked Cards API](api-specification/bank-customer-kyc-process/fetch-bank-linked-cards-api.md)
4. Linking the cards to BankEzy account the user using [Auto Link Cards API](../../../../../wallet-management/link-debit-credit-card-account/wallet-link/api-specification/multiple-card-linking-api.md)
5. For non bank customer to provide MIN KYC wallet using [Fetch Client Rules API ](api-specification/non-bank-customer-kyc-process/min-kyc-process/fetch-client-rules-api.md)and [Update KYC Details API](api-specification/non-bank-customer-kyc-process/min-kyc-process/update-kyc-details-api.md).&#x20;
6. For non bank full KYC customer please follow [`EKYC process.`](api-specification/non-bank-customer-kyc-process/ekyc-process/)





