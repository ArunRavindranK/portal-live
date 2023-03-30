# Authentication & Authorization

#### Login Flow

* When user enters Pin or device lock, app will call [login api](broken-reference) to validate profile details, pin and device details.
* Once login api return success, then app will call [fetch details api](broken-reference) to return basic details about the user, KYC data, wallet related info and VPA.
* Once app got required info it will call [fetch profile info api](broken-reference) to get how much coin, gems user gained and investment details.
* While login process, [device validation api](broken-reference) used to identify if app force update is required or user is using new device or old device. App will call [update device details api](broken-reference) if user trying to login with new device
* After login, if user wanted to change pin then [change pin api ](broken-reference)can be used also user can reset pin by calling [reset pin api](broken-reference)
* If user want to enable or disable device lock (biometric authentication), then [enable disable device lock api](broken-reference) can be used.
* User can also logout from the app anytime, for this purpose app will call [logout api](broken-reference)
