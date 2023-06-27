# EKYC Process

Full KYC through Aadhaar Number along with OTP validation.

Customer need to enter aadhaar number and OTP (to registered mobile #) to validate and complete Full kyc in BankEzy (valid for 12 months)

* When user opted for Full KYC with aadhaar, App will request user to enter aadhaar number. Once user entered Aadhar number, app will call [verify aadhar api](../../../../../version-2/customer-on-boarding/api-specification/non-bank-customer-kyc-process/ekyc-process/verify-aadhar-api.md).&#x20;
* User will get OTP registered with the entered aadhaar number. Once user entered OTP, app will call [verify aadhaar otp api](../../../../../version-2/customer-on-boarding/api-specification/non-bank-customer-kyc-process/ekyc-process/verify-aadhaar-otp-api.md)
* Once OTP verified successfully, app will show basic information to user, once user gave confirmation, app will call [verify EKYC api](../../../../../version-2/customer-on-boarding/api-specification/non-bank-customer-kyc-process/ekyc-process/verify-ekyc-api.md)
* In case to re-trigger OTP, [Resend OTP](../../../../../version-2/customer-on-boarding/api-specification/non-bank-customer-kyc-process/ekyc-process/resend-otp-api.md) Api ca be used.
