---
description: This section provides the required details for integrating the Android SDK
---

# Android

## Step 1: Gradle changes (App: build.gradle):

```
android {  
dependencies {  
    implementation(name: 'MarketPlaceSDK-release-1.01.01', ext: 'aar') 
    implementation 'org.bouncycastle:bcprov-jdk15on:1.56' 
    implementation 'com.nimbusds:nimbus-jose-jwt:9.15.2' 
    implementation 'com.amplifyframework:aws-storage-s3:1.28.2' 
    implementation 'com.amplifyframework:aws-auth-cognito:1.28.2' 
     
             }               
         } 
```

## Step 2: Get client public key

Invoke the SDK to get the client public key

```
String sdkPublicKey; 
MarketPlaceSDK marketPlaceSDK = MarketPlaceSDK.getInstance(<Activity instance to be passed>); 
    marketPlaceSDK.startMarketPlace(new WibmoConfigResponseCallback() {
     @Override 
     public void onCertificateFetchSuccess(String clientPubKey) { 
        //Will be invoked if the SDK was able to generate the certificate successfully. 
                sdkPublicKey=clientPubKey; 
        } 
 
    @Override 
    public void onCertificateFetchFailed(String errorCode, String errorDesc) {            //Will be invoked if the SDK was not able to generate the certificate due to any technical challenge. 
               //TODO App needs to handle exceptions while generating the client certificate 
            } 
        } , <PartnerCode shared offline>); 
```

## Step 3: Initialisation of SDK

Fetch the token data from your server by passing the sdkPublicKey received at step 2.

Create a JSON object from the response received.

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

Invoke the SDK by providing the JSON Object constructed in the previous step along with PartnerCode shared offline and the environment mode.

```
String partnerCode = <Data will be shared offine>; 
String envMode = “UAT”; //”UAT”, “PROD” 
String healthCheckSpanTime = “1800”; //Optional, TimeInMilliSec 
  
 To customize the healthCheckSpanTime, invoke the SDK by 
 passing health check spann time in MilliSec
      marketPlaceSDK.initializeMarketPlaceSDK(tokenObject, partnerCode, envMode, 
      healthCheckSpanTime, new WibmoInitialisationResponseCallback(){ 
      /* Need to implement methods as shown below */});
     
Sample code to invoke SDK with default health check span time 
         marketPlaceSDK.initializeMarketPlaceSDK(tokenObject, partnerCode, envMode, 
            new WibmoInitialisationResponseCallback()  
          { 
            @Override 
               public void onSDKInitialisationFailed (String errorCode, String errorDesc) { 
               //Will be invoked by the SDK if the initialization failed and control will be given back  to the app. 
               //TODO Apps needs to repeat from Step 2. 
            } 
            @Override 
            public void onSDKInitialisationComplete (String statusCode, String statusDesc) { 
                    //Will be invoked by the SDK if the initialization is success and user will be 
                      navigated to the Marketplace dashboard. 
            } 
            @Override 
            public void onTokenExpired() { 
               //Will be invoked when the token provided has expired. 
                   //TODO App needs to handle it. App should fetch the new token and should invoke 
                      the SDK starting from Step 2. 
            } 
            @Override 
            public void receiveWibmoHealthCheck () { 
                     //This will be invoked at regular interval based on healthCheckSpanTime provided 
                       else will be invoked at the default time configured in the SDK.  
            }  
 
             @Override 
            public void onSDKProcessComplete (String statusCode, String statusDesc) {   
                     //Will be invoked either when user intentionally navigates out from the SDK or the 
                       SDK forcefully quits based on any technical error.        
            } 
        }); 
```

## SDK Status code & Description

“000” - Success

“050” - Technical Error. Please retry.

## Proguard changes(App: proguard-rules.pro)

```
-keep class com.enstage.wibmo.marketplacesdk.** { *; } 
-keep class org.bouncycastle.** { *; } 
-keep class com.nimbusds.jose.** { *; } 
-keep class com.enstage.wibmo.marketplacesdk.** {*;}  
-keep class com.wibmo.** {*;} 
```

##
