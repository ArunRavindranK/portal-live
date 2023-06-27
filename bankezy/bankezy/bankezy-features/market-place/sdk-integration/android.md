# Android

## Introduction

This section provides three kinds of SDK integration support.

1. For integrating with merchants excluding recharge and bill payments merchants.

&#x20;  1.1 To display the list of popular merchants category within the SDK

&#x20;  1.2 To display the list of popular merchants category within the app. The UI and the merchant icons to be handled with in the app. In this type of integration, the list of configured merchants will be provided to the app and the app can customise the number of popular merchants, order of the merchants to be shown.

2. For integrating with recharge and bill payments merchant along with other type of merchants

## Step 1: Gradle changes (App: build.gradle): &#x20;

```
android {  
dependencies {  
    //Type 1 integration
    implementation(name: 'MarketPlaceSDK-release-1.01.01', ext: 'aar') 
    //Type 2 integration
    implementation(name: WibmoMarketPlaceSDK-release-1.00.00', ext: 'aar')
    
    implementation 'org.bouncycastle:bcprov-jdk15on:1.56' 
    implementation 'com.nimbusds:nimbus-jose-jwt:9.15.2' 
    implementation 'com.amplifyframework:aws-storage-s3:1.28.2' 
    implementation 'com.amplifyframework:aws-auth-cognito:1.28.2' 
     
             }               
         } 
```

## Step 2: Get client public key <a href="#client-public-key" id="client-public-key"></a>

Invoke the SDK to get the client public key.

String sdkPublicKey;

**Type 1 integration:**

**MarketPlaceSDK marketPlaceSDK = MarketPlaceSDK.getInstance(\<Activity instance to be passed>);**

**Type 2 integration:**&#x20;

**WibmoMarketPlaceSDK marketPlaceSDK = WibmoMarketPlaceSDK.getInstance(\<Activity instance to be passed>);**

marketPlaceSDK. startMarketPlace (new WibmoConfigResponseCallback() {

@Override

public void onCertificateFetchSuccess(String clientPubKey) {

//Will be invoked if the SDK was able to generate the certificate successfully.

sdkPublicKey=clientPubKey;

}

@Override

public void onCertificateFetchFailed(String errorCode, String errorDesc) {

//Will be invoked if the SDK was not able to generate the certificate due to any technical challenge.

//TODO App needs to handle exceptions while generating the client certificate

}

} , \<PartnerCode shared offline>);

For the specific integration to render the list of popular merchants in the app as defined in 1.2, follow the below steps after initialising as in Type 1 or Type 2 integration



## Step 3: Initialisation of SDK&#x20;

Fetch the token data from your server by passing the sdkPublicKey received at step 2.

Create a JSON object from the response received. &#x20;



```
         JSONObject tokenObject = new JSONObject(); 
         try { 
                       tokenObject.put("referenceId", <Data from server>); 
                          tokenObject.put("token", <Data from server>); 
                          tokenObject.put("expiry", <Data from server>); 
                          tokenObject.put("serverPublicKey", <Data from server>); 
                       tokenObject.put(" SDKApiKey ", <Data shared offline>); 
 
          } catch (JSONException e) { 
            e.getMessage(); 
          }
```

Invoke the SDK by providing the JSON Object constructed in the previous step along with PartnerCode shared offline and the environment mode by calling **initializeMarketPlaceSDK** method for type 1.1 and type 2 integration as defined [here](android.md#introduction).

```
String partnerCode = <Data will be shared offine>; 
String envMode = “UAT”; //”UAT”, “PROD” 
String healthCheckSpanTime = “1800”; //Optional, TimeInMilliSec 
  
      /*To customize the healthCheckSpanTime, invoke the SDK by 
      passing health check span time in MilliSec*/
      marketPlaceSDK.initializeMarketPlaceSDK(tokenObject, partnerCode, envMode, 
      healthCheckSpanTime, new WibmoInitialisationCallback(){ 
      /* Need to implement methods as shown below */
      });
     
         //Sample code to invoke SDK with default health check span time 
         marketPlaceSDK.initializeMarketPlaceSDK(tokenObject, partnerCode, envMode, 
            new WibmoInitialisationCallback()  
          { 
            @Override 
               public void onSDKInitialisationFailed (String errorCode, String errorDesc) { 
               //Will be invoked by the SDK if the initialization failed and control will be given back  to the app. 
               //TODO Apps needs to repeat from Step 2. 
            } 
            @Override 
            public void onSDKInitialisationComplete (String statusCode, String statusDesc) { 
                    //Will be invoked by the SDK if the initialization is success and user will be 
                    //navigated to the Marketplace dashboard. 
            } 
            @Override 
            public void onTokenExpired() { 
               //Will be invoked when the token provided has expired. 
                   //TODO App needs to handle it. App should fetch the new token and should invoke 
                   //the SDK starting from Step 2. 
            } 
            @Override 
            public void receiveWibmoHealthCheck () { 
                     //This will be invoked at regular interval based on healthCheckSpanTime provided 
                     //else will be invoked at the default time configured in the SDK.  
            }  
 
             @Override 
            public void onSDKProcessComplete (String statusCode, String statusDesc) {   
                     //Will be invoked either when user intentionally navigates out from the SDK or the 
                     //SDK forcefully quits based on any technical error.        
            } 
        }); 
```

Invoke the SDK by providing the JSON Object constructed in the previous step along with PartnerCode shared offline and the environment mode by calling **getMerchantList** method for type 1.2 integration as defined [here](android.md#introduction)

marketPlaceSDK.getMerchantList (tokenObject, partnerCode, envMode,

&#x20;           new WibmoInitialisationCallBack()

&#x20;          {

&#x20;            @Override

&#x20;            public void onSDKInitialisationFailed (String errorCode, String errorDesc) {

&#x20;            //Will be invoked by the SDK if the initialization failed and control will be given back to the app.

&#x20;            //TODO Apps needs to repeat from Step 2.

&#x20;           }

&#x20;           @Override

&#x20;           public void onSDKInitialisationComplete (String statusCode, String statusDesc) {

&#x20;                   //Will be invoked by the SDK if the initialization is success and user will be

&#x20;                    // navigated to the Marketplace dashboard.

&#x20;           }

&#x20;           @Override

&#x20;           public void onTokenExpired() {

&#x20;           //Will be invoked when the token provided has expired.

&#x20;           //TODO App needs to handle it. App should fetch the new token and should invoke the SDK starting from Step 2.

&#x20;           }

&#x20;           @Override

&#x20;           public void receiveWibmoHealthCheck () {

&#x20;            //This will be not be invoked at regular interval based on healthCheckSpanTime provided in onMerchantClick else will be invoked at the default time configured in the SDK.

&#x20;           }

&#x20;           @Override

&#x20;           public void onSDKProcessComplete (String statusCode, String statusDesc) {&#x20;

&#x20;           //Will be invoked either when user intentionally navigates out from the SDK or the SDK    forcefully quits based on any technical error.     &#x20;

&#x20;           }

}, new GetMerchantListInterface() {

&#x20;           @Override\
&#x20;           public void onFetchMerchantListSuccess(List\<MerchantDataList> merchantDataList {}

```
     @Override

     public void onFetchMerchantListFailure(int resCode, String resDesc) {}
});
```

On selection of a particular merchant in the app, invoke the below SDK method

```
     marketPlaceSDK.onMerchantClick(<merchant code>, String healthCheckSpanTime);
```

## SDK Status code & Description          &#x20;

&#x20;        “000” - Success&#x20;

&#x20;        “050” - Technical Error. Please retry.&#x20;

## Proguard changes(App: proguard-rules.pro)&#x20;

```
-keep class com.enstage.wibmo.marketplacesdk.** { *; } 
-keep class org.bouncycastle.** { *; } 
-keep class com.nimbusds.jose.** { *; } 
-keep class com.enstage.wibmo.marketplacesdk.** {*;}  
-keep class com.wibmo.** {*;} 
```

##
