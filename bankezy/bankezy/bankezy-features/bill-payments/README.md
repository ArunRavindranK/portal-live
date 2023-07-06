# Bill Payments

Bankezy powered by BBPS offers services to do Mobile and DTH Recharge, fetch and pay the utility bills in a seamless manner.

Bharat Bill Payment Services (BBPS) is a digital platform which offers bill payments services by aggregating billers across many categories.

Bankezy powered by PayU Connect offers customer journeys designed as per BBPS guidelines. One can embed ready-to-go BBPS bill payments or can design screens with our APIs



The below diagram represents the sequence of flows for various types of bill payments.

&#x20;&#x20;

<figure><img src="../../../../.gitbook/assets/Retail Flow Diagram - Retail  (1).jpeg" alt=""><figcaption></figcaption></figure>

#### The following are different types of flows for Bill Payment

1. **Mobile Prepaid**

&#x20;          1\. User can fetch operator and circle info of the mobile number [Operator Circle Info API](recharge/version-v1/operator-circle-info-api.md)

&#x20;        2\. To get list of operators [Operator List API](recharge/version-v1/operator-list-api.md)

&#x20;        3\. To get list of circles [Circle List API](recharge/version-v1/circle-list-api.md)

&#x20;        4\. To get list of recharge plans for operator and circle [Recharge Plans API](recharge/version-v1/recharge-plans-api.md)

&#x20;        5\. To validate recharge request with out calling SP [Validation Init API](common-api/version-1/validation-init-api.md)

&#x20;        6\. To validate recharge request by calling SP [Payment Validation API](common-api/version-1/payment-validation-api.md)

&#x20;        7\. To make recharge transaction for the selected amount [Recharge Request API](recharge/version-v1/recharge-request-api.md)

2. **Mobile PostPaid**
   1. User can fetch operator and circle info of the mobile number [Operator Circle Info API](recharge/version-v1/operator-circle-info-api.md)

&#x20;        2\. To get list of operators [Operator List API](recharge/version-v1/operator-list-api.md)

&#x20;        3\. To get list of circles [Circle List API](recharge/version-v1/circle-list-api.md)

&#x20;        4\. To get billers for the selected category [Biller list By categoryId API](utility-payment/version-1/biller-list-by-categoryid-api.md)

&#x20;       5\.  To fetch user bill [Bill Fetch API](utility-payment/version-1/bill-fetch-api.md)

&#x20;       6\. To validate recharge request with out calling SP [Validation Init API](common-api/version-1/validation-init-api.md)

&#x20;       7\.  To validate recharge request by calling SP [Payment Validation API](common-api/version-1/payment-validation-api.md)

&#x20;        8\. To make recharge transaction for the selected amount [Recharge Request API](recharge/version-v1/recharge-request-api.md)

3. **Electricity**
   1. To get billers for the selected category [Biller list By categoryId API](utility-payment/version-1/biller-list-by-categoryid-api.md)
   2. To get billers for the billerId [Biller Details By BillerId API](utility-payment/version-1/biller-details-by-billerid-api.md)
   3. To fetch user bill [Bill Fetch API](utility-payment/version-1/bill-fetch-api.md)
   4. To validate recharge request with out calling SP [Validation Init API](common-api/version-1/validation-init-api.md)
   5. &#x20;To validate recharge request by calling SP [Payment Validation API](common-api/version-1/payment-validation-api.md)
   6. To make recharge transaction for the selected amount [Recharge Request API](recharge/version-v1/recharge-request-api.md)           &#x20;
4. **DTH**
   1. To get list of operators [Operator List API](recharge/version-v1/operator-list-api.md)
   2. To validate recharge request with out calling SP [Validation Init API](common-api/version-1/validation-init-api.md)
   3. &#x20;To validate recharge request by calling SP [Payment Validation API](common-api/version-1/payment-validation-api.md)
   4. To make recharge transaction for the selected amount [Recharge Request API](recharge/version-v1/recharge-request-api.md)&#x20;

**Following are the few other API's that are used for all categories**

&#x20;     1\. For displaying list of [Categories API](common-api/version-1/categories-api.md)

&#x20;    2\. To check list of transactions  [Transaction History API](common-api/version-1/transaction-history-api.md) Should be used

&#x20; &#x20;







