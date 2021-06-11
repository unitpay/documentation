# Creating a payment \(widget\)

A widget is a pop-up window with a payment form. To use the widget, you just need to add its code to the site page, configure the transfer of parameters and create an event for its call \(for example, clicking on a button\). The example code and description of the used widget parameters are located in the Unitpay personal account in the project settings on the "Payment widget" tab \(at the screenshot below\).

![Location of the widget code in the project settings](../.gitbook/assets/image%20%2870%29.png)

## Example code:

```text
<script src="https://widget.unitpay.money/unitpay.js"></script>
<script type="text/javascript">
this.pay = function() {
var payment = new UnitPay();
payment.createWidget({
publicKey: "PUBLIC KEY",
sum: 1,
account: "demo",
domainName: "unitpay.money",
signature: "2c38bb3114b2f02222ee35f6b60c6bbe628ad31bed59633787204ae59659a02e",
desc: "Описание платежа",
locale: "ru",
});
payment.success(function (params) {
console.log('Успешный платеж');
});
payment.error(function (message, params) {
console.log(message);
});
return false;
};
</script>
```

**Обязательные параметры:**

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left">Value</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>publicKey</b>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Public key. You can find it under the Settings Tab of your project</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>sum</b>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Payment amount (for example, 10.00)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>account</b>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Customer ID in your system (e-mail or order number, for example)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>domainName</b>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">unitpay.money</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>signature</b>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>Digital signature. It is formed as sha256 (account + &quot;{up}&quot;
          + currency + &quot;{up}&quot; + desc + &quot;{up}&quot; + sum + &quot;{up}&quot;
          + secretKey),
          <br />where <b>sha256</b> is the hashing method;
          <br /><b>{up}</b> is the parameter separator in the hash function;
          <br /><b>account, sum, currency, desc</b> are the payment initialization parameters
          described above;
          <br /><b>secretKey</b> is the secret key of the project (available in your personal
          account);</p>
        <p><b>Important Note</b>. If you do not transmit <b>currency</b> to the payment
          form, this parameter should not be used in signature generation.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>desc</b>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">The order&apos;s description for customer</td>
    </tr>
  </tbody>
</table>

**Additional parameters:**

|  | Value | Description |
| :--- | :--- | :--- |
| **locale** | ru, en | Forcing the language of the widget. |
| **currency** | string | The order currency according to ISO 4217 \(RUB, UAH, BYN, EUR, USD etc. [Currency codes](../book-of-reference/currency-codes.md)\). If the payment system does not support the required currency, the amount will be converted to the payment system currency. |
| **paymentType** | string | [Code of the payment system](../book-of-reference/payment-system-codes.md), through which the payment will be made. |
| **hideMenu** | true, false | It hides the menu with the payment method options. |

{% hint style="warning" %}
If you'll have any additional questions during the integration, you can ask them to our customer support - in Unit.Help or send your questions to manager@unitpay.money
{% endhint %}

