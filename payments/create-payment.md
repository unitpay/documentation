# Creating a payment

To interact with the API, use the [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk) library.

![](../.gitbook/assets/image%20%2818%29.png)

**Required parameters:**

|  | Type | **Description** |
| :--- | :--- | :--- |
| **paymentType** | line | [Code of the payment system](../book-of-reference/payment-system-codes.md) through which the payment will be made |
| **account** | line | Subscriber ID in the partner's system \(for example, the subscriber's login or email\) |
| **sum** | number | Amount of payment in rubles \(for example, 10.00\) |
| **projectId** | number | Your project ID in the UnitPay system |
| **resultUrl** | line | Url encoded branching address to which the user is sent after payment \(for example, [http://yoursite.ru](http://unitpay.money/)\). If this parameter is not set, the address of the payment receipt page will be used. |
| **desc** | line | Order description |
| **ip** | line | Payer's IP address |
| **secretKey** | line | Secret key, available in the project settings |

**Parameters depending on the type of payment:**

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| phone | number | Phone number with country code \(for example, 79520000000\) |
| operator | line | [Operator's alphabetic code](../book-of-reference/operator-codes.md) for SMS billing. For other systems, the operator is determined automatically |

**Additional payment parameters:**

\*\*\*\*

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **currency** | line | The order currency according to ISO 4217 \(RUB, UAH, BYN, EUR, USD etc. [Currency codes](../book-of-reference/currency-codes.md)\). If the payment system does not support the required currency, the amount will be converted to the payment system currency |
| **locale** | line | It is mandatory to specify the payment form language, acceptable values: ru, en. By default, the form language is determined based on the country that the user's IP address belongs to |
| **signature** | line | Request digital signature. This feature is mandatory for all new Unitpay partners. It protects you from hackers: substituting the description or price of the order, placing a link to the payment on the resources of fraudsters. |
| **backUrl** | line | The user's return address from the payment form without making a purchase; the project address is used by default. The project domain must be used in the address. Examples: [https://redirect.&lt;project](https://redirect.<project) domain&gt;/?someParams", "[https://&lt;project](https://<project) domain&gt;/redirect/ |
| **subscription** | true/false | Use this flag if you want to create a subscription under the payer's card. The subscription ID \(subscriptionId\) will be transmitted in the PAY method to your payment handler. Subscriptions can only be used after approval by your supervising manager |
| **subscriptionId** | number | The subscription ID in respect of which it is necessary to debit the funds. This parameter should be previously received in the PAY method to your payment handler |
| **preauth** | true/false | Use this flag to create a payment with pre-authorization. By default, this flag is disabled and the value is 0 |
| **preauthExpireLogic** | number | Field for the logic of payment blocking with pre-authorization     0 - If there is no request for confirmation or cancellation, payment will be confirmed upon expiration of the lock on the side of the acquirer bank \(~114 hours after creating the payment\)  1 - If there is no request for confirmation or cancellation, payment will be cancelled upon expiration of the lock on the side of the acquirer bank \(~114 hours after creating the payment\).  If the parameter is not used, the payment will be cancelled after the expiration date. |

You can run the query in test mode. [Learn more](../other/test-api.md)

**Request digital signature**

For additional security of your payments, we perform mandatory verification of the digital signature when creating a payment. The signature guarantees protection against the substitution of the transmitted values \(e.g., changing the payment amount or order number\).

![](../.gitbook/assets/image%20%2821%29.png)

\*\*\*\*

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **signature** | line | Digital signature. It is formed as sha256\( account + "{up}" + currency + "{up}" + desc + "{up}" + sum + "{up}" + secretKey\),   where **sha256** is the hashing method;    **"{up}"** is the parameter separator in the hash function;  **account**, **sum**, **currency**, **desc**  are the payment initialization parameters described above;  **secretKey**  is the secret key of the project \(available in your personal account\);    **Important Note**. If you do not transmit **currency** to the payment form, this parameter should not be used in signature generation. |

**Пример формирования цифровой подписи на PHP:**

```text
function getFormSignature($account, $currency, $desc, $sum, $secretKey) {
    $hashStr = $account.'{up}'.$currency.'{up}'.$desc.'{up}'.$sum.'{up}'.$secretKey;
    return hash('sha256', $hashStr);
}
```

**Пример формирования цифровой подписи на Perl:**

```text
sub getSignature {
    my ($method, $params, $secretKey) = @_;
    delete $params-&gt;{sign};
    delete $params-&gt;{signature};
    my $s = $method;
    foreach my $key (sort keys %{$params}) {
        $s .= '{up}' . $params-&gt;{$key};
    }
    $s .= '{up}' . $secretKey;
    use Digest::SHA qw(sha256_hex);
    return sha256_hex($s);
}
```

**Successful response**

```text
{"result": {
    "message": "Платеж успешно создан.",
    "paymentId": "1400072",  
    "type": "redirect", 
    "redirectUrl": "http://unitpay.money/pay/redirect/111-ab34c22" 
}}
```

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | Information about the result of payment generation |
| **type** | line | redirect — requires redirection to the payment platform gateway  invoice — invoice is generated automatically, payment is made by the user through the payment system's account |
| **paymentId** | number | Payment number in the UnitPay system |
| **redirectUrl** | line | URL for redirecting the user to the payment platform gateway. If the payment does not require redirecting, this parameter will not be available |

## Error response

```text
{"error": {
    "message": "Описание ошибки"
}}
```

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | Information with a description of the payment generation error |

