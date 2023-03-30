# EKYC Process

Full KYC through Aadhar Number along with OTP validation.

Customer need to enter aadhar number and OTP (to registered mobile #) to validate and complete Full kyc in BankEzy (valid for 12 months)

* When user opted for Full KYC with aadhar, App will request user to enter aadhar number. Once user entered Aadhar number, app will call [verify aadhar api](verify-aadhar-api.md).&#x20;
* User will get OTP registered with the entered aadhar number. Once user entered OTP, app will call [verify aadhar otp api](verify-aadhaar-otp-api.md)
* Once OTP verified successfully, app will show basic information to user, once user gave confirmation, app will call [verify EKYC api](verify-ekyc-api.md)
