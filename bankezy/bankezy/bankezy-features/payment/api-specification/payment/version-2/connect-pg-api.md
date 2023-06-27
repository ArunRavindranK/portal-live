---
description: This API used to connect payU PG to checkout transaction.
---

# Connect PG API

{% swagger method="post" path="" baseUrl="/redirect/payments/v1/txn/connect/pg" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" type="String" required="true" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-parameter in="body" name="request" type="String" required="true" %}
Concat value of merchant Id & txnId
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST 'http://localhost:2442/redirect/payments/v1/txn/connect/pg' \
--header 'X-PROGRAM-ID: 1111' \
--header 'Content-Type: text/plain' \
--header 'Cookie: JSESSIONID=8CEC7C43996D57C3E7A7BE123530348F' \
--data-raw 'merchantId=81516121&txnId=2023053012344556'
```
{% endtab %}

{% tab title="Request Sample" %}
```
merchantId=81516121&txnId=2023053012344556
```
{% endtab %}

{% tab title="Response Sample" %}


```html
<html lang="en">

<head>
	<title>QR-code page</title>
	<meta charset="utf-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<meta name="description" content="">
	<meta name="keywords" content="">
	<meta name="author" content="">

<body>
	<div style="margin:auto;width:100%;text-align:center;font-size:20px;font-weight:200;">Please wait.....</div>

	<form method="post"
		action="https://user4.pcdev.enstage-sas.com/kong/redirect/payments/responseFromPg?X-API-KEY=REDIRECT_MERCHANT_2002"
		id="merchantReturn" name="merchantReturn">
		<input type="hidden" name="wibmoTxnId" value="2023051620013010007">
		<input type="hidden" name="chargeAttempted" value="true">
		<input type="hidden" name="resDesc" value="SUCCESS">
		<input type="hidden" name="cardType" value="MAST">
		<input type="hidden" name="cardToken" value="1234567fsd234">
		<input type="hidden" name="mode" value="LC">
		<input type="hidden" name="issuingBank" value="">
		<input type="hidden" name="cardNum" value="">
		<input type="hidden" name="isConsent" value="true">
		<input type="hidden" name="resCode" value="200">
		<input type="hidden" name="txnAmt" value="10000">
		<input type="hidden" name="merTxnId" value="202305161114371130dS98sQ5">
		<input type="hidden" name="txnDate" value="1685111254857">

</body>
		<script>
			var formParams1=[];
        formParams1.push({"id":"wibmoTxnId", "value":"2023051620013010007"});
        formParams1.push({"id":"chargeAttempted", "value":"true"});
        formParams1.push({"id":"resDesc", "value":"SUCCESS"});
        formParams1.push({"id":"cardType", "value":"MAST"});
        formParams1.push({"id":"cardToken", "value":"1234567fsd234"});
        formParams1.push({"id":"mode", "value":"LC"});
        formParams1.push({"id":"issuingBank", "value":""});
        formParams1.push({"id":"cardNum", "value":""});
        formParams1.push({"id":"isConsent", "value":"true"});
        formParams1.push({"id":"resCode", "value":"200"});
        formParams1.push({"id":"txnAmt", "value":"10000"});
        formParams1.push({"id":"merTxnId", "value":"202305161114371130dS98sQ5"});
        formParams1.push({"id":"txnDate", "value":"1685111254857"});
if(window.HTMLOUT && window.HTMLOUT.processResponseData){
      setTimeout(function(){
        window.HTMLOUT.processResponseData(JSON.stringify(formParams1));
      }, 100);
}else if (window.webkit && window.webkit.messageHandlers && window.webkit.messageHandlers.HTMLOUT){
 	window.webkit.messageHandlers.HTMLOUT.postMessage(JSON.stringify(formParams1));
 }else{
	document.merchantReturn.submit();
}

		</script>

</html>
```
{% endtab %}
{% endtabs %}
