# Authentication & Authorization

#### Login Flow

* When user enters Pin or device lock, app will call [login api](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/login-api.md) to validate profile details, pin and device details.
* Once login api return success, then app will call [fetch details api](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/fetch-details-api.md) to return basic details about the user, KYC data, wallet related info and VPA.
* Once app got required info it will call [fetch profile info api](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/fetch-profile-details-api.md) to get how much coin, gems user gained and investment details.
* While login process, [device validation api](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/device-validation-api.md) used to identify if app force update is required or user is using new device or old device. App will call [update device details api](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/update-device-details-api.md) if user trying to login with new device
* After login, if user wanted to change pin then [change pin api ](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/change-pin-api.md)can be used also user can reset pin by calling [reset pin api](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/reset-pin-api.md)
* If user want to enable or disable device lock (biometric authentication), then [enable disable device lock api](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/enable-disable-device-lock-api.md) can be used.
* User can also logout from the app anytime, for this purpose app will call [logout api](../../../../version-1/customer-on-boarding/api-specification/authentication-and-authorization/logout-api.md)
