---
description: >-
  This Api returns all the transaction done by user based on the filter
  criteria(like date, merchants, card type, status..)
---

# Fetch Transactions API

{% swagger method="post" path="" baseUrl="<domain>/txnHistory/fetch/v1" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-API-TOKEN  " type="String" required="true" %}
The token got from the login API
{% endswagger-parameter %}

{% swagger-parameter in="body" name="action" type="String" required="true" %}
Action(Ex: MER_TXN,P2P,RM)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fromDate" type="String" required="true" %}
From Date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="merCategory" type="String" required="true" %}
​Merchant Category
{% endswagger-parameter %}

{% swagger-parameter in="body" name="paymentMode" type="String" required="true" %}
​Payment mode
{% endswagger-parameter %}

{% swagger-parameter in="body" name="toDate" type="String" required="true" %}
​To Date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnCategory" type="String" required="true" %}
Category(Ex: LM,P2PC,P2PD)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="txnStatus" type="String" required="true" %}
Transaction Status
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-API-KEY" required="false" %}
MOB-APP-2001
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="201: Created" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Custom response codes

| Code | Description                        |
| ---- | ---------------------------------- |
| ​37  | Amount is zero                     |
| 65   | ​Bank id is empty                  |
| 101  | Transaction Type is Mandatory      |
| 120  | Beneficiary id should not be zero. |

{% tabs %}
{% tab title="Sample curl command" %}
```json
curl --location --request POST '
https://payment1.pcdev.enstage-sas.com/txnHistory/fetch/v1'
\--header 'X-API-KEY: MOB-APP-2001'
\--header 'Content-Type: text/plain'
\--header 'X-API-TOKEN:token'
--data-raw'{ "fromDate": "2022-04-29", "toDate": "2022-07-29" }'
```
{% endtab %}

{% tab title="Request sample" %}
```json
{
  "fromDate": "2022-04-29",
  "toDate": "2022-07-29"
}
```
{% endtab %}

{% tab title="Response sample" %}
```json
{
  "resCode": "200",
  "resDesc": "Txn History Fetched Successfully",
  "data": [
    {
      "originalTxnId": "11112022061310033936619177622436076",
      "sourceAccount": null,
      "txnDateStr": "10:03 AM, 13 June 2022",
      "paymentMode": "UPII",
      "merCategory": "Purchase",
      "merName": "",
      "txnShortDesc": "Test Merchant",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "IAP",
      "merId": "81516121",
      "txnDesc": "Paid Rs. 79.00 to Test Merchant",
      "txnDate": 1655114625000,
      "txnAmount": 7900,
      "txnFlow": "O",
      "txnId": "489610"
    },
    {
      "originalTxnId": "11112022061012270051836479280816461",
      "sourceAccount": null,
      "txnDateStr": "12:27 PM, 10 June 2022",
      "paymentMode": "UPII",
      "merCategory": "Purchase",
      "merName": "",
      "txnShortDesc": "Test Merchant",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "IAP",
      "merId": "81516121",
      "txnDesc": "Paid Rs. 79.00 to Test Merchant",
      "txnDate": 1654864031000,
      "txnAmount": 7900,
      "txnFlow": "O",
      "txnId": "489609"
    },
    {
      "originalTxnId": "202206100923307678oA25uD4",
      "sourceAccount": null,
      "txnDateStr": "09:23 AM, 10 June 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 1.00 to BankEzy Wallet",
      "txnDate": 1654853029000,
      "txnAmount": 100,
      "txnFlow": "I",
      "txnId": "489543"
    },
    {
      "originalTxnId": "202206100923307678oA25uD4",
      "sourceAccount": null,
      "txnDateStr": "09:23 AM, 10 June 2022",
      "paymentMode": "UPII",
      "merCategory": "Purchase",
      "merName": "",
      "txnShortDesc": "Load Money. Merchant",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "LM",
      "merId": "171756421435003980",
      "txnDesc": "Paid Rs. 1.00 to Load Money. Merchant",
      "txnDate": 1654853013000,
      "txnAmount": 100,
      "txnFlow": "O",
      "txnId": "489542"
    },
    {
      "originalTxnId": "202206100921248521lC14mU7",
      "sourceAccount": null,
      "txnDateStr": "09:21 AM, 10 June 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 1.00 to BankEzy Wallet",
      "txnDate": 1654852894000,
      "txnAmount": 100,
      "txnFlow": "I",
      "txnId": "489541"
    },
    {
      "originalTxnId": "202206100921248521lC14mU7",
      "sourceAccount": null,
      "txnDateStr": "09:21 AM, 10 June 2022",
      "paymentMode": "UPII",
      "merCategory": "Purchase",
      "merName": "",
      "txnShortDesc": "Load Money. Merchant",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "LM",
      "merId": "171756421435003980",
      "txnDesc": "Paid Rs. 1.00 to Load Money. Merchant",
      "txnDate": 1654852889000,
      "txnAmount": 100,
      "txnFlow": "O",
      "txnId": "489540"
    },
    {
      "originalTxnId": "202206100841349346mL19iC4",
      "sourceAccount": null,
      "txnDateStr": "08:42 AM, 10 June 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 1.00 to BankEzy Wallet",
      "txnDate": 1654850520000,
      "txnAmount": 100,
      "txnFlow": "I",
      "txnId": "489512"
    },
    {
      "originalTxnId": "202206100841349346mL19iC4",
      "sourceAccount": null,
      "txnDateStr": "08:41 AM, 10 June 2022",
      "paymentMode": "UPII",
      "merCategory": "Purchase",
      "merName": "UPI Payment",
      "txnShortDesc": "UPI Payment",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "LM",
      "merId": "171756421435003980",
      "txnDesc": "Paid Rs. 1.00 to UPI Payment",
      "txnDate": 1654850496000,
      "txnAmount": 100,
      "txnFlow": "O",
      "txnId": "489511"
    },
    {
      "originalTxnId": "202206100839310430hZ32pK2",
      "sourceAccount": null,
      "txnDateStr": "08:39 AM, 10 June 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 1.00 to BankEzy Wallet",
      "txnDate": 1654850385000,
      "txnAmount": 100,
      "txnFlow": "I",
      "txnId": "489510"
    },
    {
      "originalTxnId": "202206100839310430hZ32pK2",
      "sourceAccount": null,
      "txnDateStr": "08:39 AM, 10 June 2022",
      "paymentMode": "UPII",
      "merCategory": "Purchase",
      "merName": "UPI Payment",
      "txnShortDesc": "UPI Payment",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "LM",
      "merId": "171756421435003980",
      "txnDesc": "Paid Rs. 1.00 to UPI Payment",
      "txnDate": 1654850374000,
      "txnAmount": 100,
      "txnFlow": "O",
      "txnId": "489509"
    },
    {
      "originalTxnId": "202206091150587014qI98oY7",
      "sourceAccount": null,
      "txnDateStr": "11:55 AM, 09 June 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 1.00 to BankEzy Wallet",
      "txnDate": 1654775740000,
      "txnAmount": 100,
      "txnFlow": "I",
      "txnId": "489444"
    },
    {
      "originalTxnId": "202206091150587014qI98oY7",
      "sourceAccount": null,
      "txnDateStr": "11:55 AM, 09 June 2022",
      "paymentMode": "UPII",
      "merCategory": "Others",
      "merName": "Load Money. Merchant",
      "txnShortDesc": "Load Money. Merchant",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "LM",
      "merId": "171756421435003980",
      "txnDesc": "Paid Rs. 1.00 to Load Money. Merchant",
      "txnDate": 1654775739000,
      "txnAmount": 100,
      "txnFlow": "O",
      "txnId": "489443"
    },
    {
      "originalTxnId": "202206090915269651sX15dN5",
      "sourceAccount": null,
      "txnDateStr": "09:16 AM, 09 June 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 1.00 to BankEzy Wallet",
      "txnDate": 1654766164000,
      "txnAmount": 100,
      "txnFlow": "I",
      "txnId": "489440"
    },
    {
      "originalTxnId": "202206090915269651sX15dN5",
      "sourceAccount": null,
      "txnDateStr": "09:15 AM, 09 June 2022",
      "paymentMode": "UPII",
      "merCategory": "Others",
      "merName": "Load Money. Merchant",
      "txnShortDesc": "Load Money. Merchant",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "LM",
      "merId": "171756421435003980",
      "txnDesc": "Paid Rs. 1.00 to Load Money. Merchant",
      "txnDate": 1654766159000,
      "txnAmount": 100,
      "txnFlow": "O",
      "txnId": "489439"
    },
    {
      "originalTxnId": "202206030734459240oY72qW1",
      "sourceAccount": null,
      "txnDateStr": "07:35 AM, 03 June 2022",
      "paymentMode": "UPII",
      "merCategory": "Others",
      "merName": "Load Money. Merchant",
      "txnShortDesc": "Load Money. Merchant",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "LM",
      "merId": "171756421435003980",
      "txnDesc": "Paid Rs. 1.00 to Load Money. Merchant",
      "txnDate": 1654241717000,
      "txnAmount": 100,
      "txnFlow": "O",
      "txnId": "489395"
    },
    {
      "originalTxnId": "202205201042136493pT23nM4",
      "sourceAccount": null,
      "txnDateStr": "10:42 AM, 20 May 2022",
      "paymentMode": "UPII",
      "merCategory": "Others",
      "merName": "Load Money. Merchant",
      "txnShortDesc": "Load Money. Merchant",
      "destAccount": null,
      "txnStatus": "F",
      "action": "MER_TXN",
      "txnCategory": "LM",
      "merId": "171756421435003980",
      "txnDesc": "Paid Rs. 1.00 to Load Money. Merchant",
      "txnDate": 1653043347000,
      "txnAmount": 100,
      "txnFlow": "O",
      "txnId": "489304"
    },
    {
      "originalTxnId": "202205170924415026qO58kQ2",
      "sourceAccount": null,
      "txnDateStr": "09:24 AM, 17 May 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "Kumudha Glory ",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "W2A",
      "txnCategory": "Refund",
      "merId": null,
      "txnDesc": "Refunded 1.02 to BankEzy Wallet",
      "txnDate": 1652779484000,
      "txnAmount": 102,
      "txnFlow": "I",
      "txnId": "489274"
    },
    {
      "originalTxnId": "202205170924415026qO58kQ2",
      "sourceAccount": "**** **** **** 4879",
      "txnDateStr": "09:24 AM, 17 May 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "Kumudha Glory ",
      "destAccount": "**** **** 9012",
      "txnStatus": "P",
      "action": "W2A",
      "txnCategory": "W2AD",
      "merId": null,
      "txnDesc": "Sent 1.00 to Kumudha Glory ",
      "txnDate": 1652779482000,
      "txnAmount": 102,
      "txnFlow": "O",
      "txnId": "489273"
    },
    {
      "originalTxnId": "202205131313293913lY87oH8",
      "sourceAccount": "**** **** **** 3398",
      "txnDateStr": "02:13 PM, 13 May 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 1.00 to BankEzy Wallet",
      "txnDate": 1652451217000,
      "txnAmount": 100,
      "txnFlow": "I",
      "txnId": "489264"
    },
    {
      "originalTxnId": "202205131302460780eA34vI0",
      "sourceAccount": "**** **** **** 3398",
      "txnDateStr": "02:02 PM, 13 May 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 100.00 to BankEzy Wallet",
      "txnDate": 1652450571000,
      "txnAmount": 10000,
      "txnFlow": "I",
      "txnId": "489263"
    },
    {
      "originalTxnId": "202205131259354052zM38lZ3",
      "sourceAccount": "**** **** **** 3398",
      "txnDateStr": "01:59 PM, 13 May 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 100.00 to BankEzy Wallet",
      "txnDate": 1652450389000,
      "txnAmount": 10000,
      "txnFlow": "I",
      "txnId": "489262"
    },
    {
      "originalTxnId": "202205131313293913lY87oH8",
      "sourceAccount": "**** **** **** 3398",
      "txnDateStr": "01:13 PM, 13 May 2022",
      "paymentMode": "D",
      "merCategory": "Others",
      "merName": "Load Money. Merchant",
      "txnShortDesc": "Load Money. Merchant",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "LM",
      "merId": "171756421435003980",
      "txnDesc": "Paid Rs. 1.00 to Load Money. Merchant",
      "txnDate": 1652447616000,
      "txnAmount": 100,
      "txnFlow": "O",
      "txnId": "489261"
    },
    {
      "originalTxnId": "202205131302460780eA34vI0",
      "sourceAccount": "**** **** **** 3398",
      "txnDateStr": "01:03 PM, 13 May 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 100.00 to BankEzy Wallet",
      "txnDate": 1652447030000,
      "txnAmount": 10000,
      "txnFlow": "I",
      "txnId": "489260"
    },
    {
      "originalTxnId": "202205051236014482pQ52nW0",
      "sourceAccount": "**** **** **** 3398",
      "txnDateStr": "12:36 PM, 05 May 2022",
      "paymentMode": "RW",
      "merCategory": "Others",
      "merName": null,
      "txnShortDesc": "BankEzy Wallet XX 4879",
      "destAccount": "**** **** **** 4879",
      "txnStatus": "S",
      "action": "LM",
      "txnCategory": "LM",
      "merId": null,
      "txnDesc": "Added 1000.00 to BankEzy Wallet",
      "txnDate": 1651754178000,
      "txnAmount": 100000,
      "txnFlow": "I",
      "txnId": "489177"
    },
    {
      "originalTxnId": "202205051236014482pQ52nW0",
      "sourceAccount": "**** **** **** 3398",
      "txnDateStr": "12:36 PM, 05 May 2022",
      "paymentMode": "D",
      "merCategory": "Others",
      "merName": "Load Money. Merchant",
      "txnShortDesc": "Load Money. Merchant",
      "destAccount": null,
      "txnStatus": "S",
      "action": "MER_TXN",
      "txnCategory": "LM",
      "merId": "171756421435003980",
      "txnDesc": "Paid Rs. 1,000.00 to Load Money. Merchant",
      "txnDate": 1651754177000,
      "txnAmount": 100000,
      "txnFlow": "O",
      "txnId": "489176"
    }
  ]
}
```
{% endtab %}
{% endtabs %}
