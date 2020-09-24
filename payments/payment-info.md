# Payment information

To interact with the API, use the [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk) library.

To get information about the payment, run GET query:

![](../.gitbook/assets/image%20%2867%29.png)

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **paymentId** | number | Payment ID in the UnitPay system. |
| **secretKey** | line | Project secret key. |

You can run the query in test mode. [Learn more](../other/test-api.md)

**Successful response**

![](../.gitbook/assets/image%20%2843%29.png)

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **status** | line | success — successful payment;   wait — payment is pending;   error — payment error;  error\_pay — error/failure of the store at the PAY stage; in statistics, it is displayed as "incomplete";   error\_check — error/failure of the store at the CHECK stage, in statistics it is displayed as "rejected";   refund — refund to the buyer;   secure — being verified by the Bank's security service. |
| **paymentId** | number | Payment ID in the UnitPay system |
| **projectId** | number | Project ID in the UnitPay system |
| **account** | line | Client \(order\) ID in the partner's system |
| **purse** | line | Purse \(account number\) from which the payment was made |
| **profit** | number | Your income from this payment, rubles |
| **paymentType** | line | [Payment system code](../book-of-reference/payment-system-codes.md) |
| **orderSum** | number | Order amount. Make sure to check this value against the original order amount |
| **orderCurrency** | line | Order currency \(RUB, UAH, BYN, EUR, USD\). Make sure to check this value with the original order currency |
| **date** | line | Payment date in the YYYY-mm-dd HH:ii:ss format \(for example, 2012-10-01 12:32:00\) |
| **payerSum** | number | Amount debited from the subscriber's account |
| **payerCurrency** | line | Currency of debiting from the subscriber's account according to ISO 4217 standard \(RUB, UAH, BYN, EUR, USD\) |
| **errorMessage** | line | Error details \(only for the error status\) |

**Error response**

![](../.gitbook/assets/image%20%2834%29.png)

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | Information with a description of the request error. |

