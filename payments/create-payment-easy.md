# Creating a payment \(easy way\)



{% hint style="info" %}
If your website was created using CMS please take a look at the list of our [modules](../modules/cms-modules/).
{% endhint %}

To initiate a payment through a single form of payment, you just need to direct the user to a special URL and transfer a number of required parameters.

{% api-method method="get" host="" path="https://unitpay.money/pay/PUBLICKEY?sum&account&desc&signature" %}
{% api-method-summary %}
pay
{% endapi-method-summary %}

{% api-method-description %}
The request is used to initialize a payment
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="publickey" type="string" required=true %}
public key. You can find it under the Settings tab of your project
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="backurl" type="string" required=false %}
The user's return address from the payment form without making a purchase; the project address is used by default. The project domain must be used in the address. Examples: https://redirect.&lt;project domain&gt;/?someParams", "https://&lt;project domain&gt;/redirect/
{% endapi-method-parameter %}

{% api-method-parameter name="locale" type="string" required=false %}
It is mandatory to specify the payment form language, acceptable values: ru, en. By default, the form language is determined based on the country that the user's IP address belongs to
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="string" required=false %}
The order currency according to ISO 4217 \(RUB, UAH, BYN, EUR, USD\). If the payment system does not support the required currency, the amount will be converted to the payment system currency
{% endapi-method-parameter %}

{% api-method-parameter name="signature" type="string" required=true %}
It protects you from hackers: substituting the description or price of the order, placing a link to the payment on the resources of fraudsters.
{% endapi-method-parameter %}

{% api-method-parameter name="desc" type="string" required=true %}
Order description. It is used only for informing when making a payment
{% endapi-method-parameter %}

{% api-method-parameter name="account" type="string" required=true %}
Subscriber ID in your system \(for example, email or order number\).
{% endapi-method-parameter %}

{% api-method-parameter name="sum" type="number" required=true %}
Payment amount. In rubles by default. See the additional currency parameter
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

**Example:**

```text
https://unitpay.money/pay/111111-11111?sum=100&account=222111&desc=Online%20course&signature=2c38bb3114b2f02222ee35f6b60c6bbe628ad31bed59633787204ae59659a02e
```

\*\*\*\*

**PUBLIC KEY**: The value of the project public key can be found on the project page in the special Payment Form section of your personal account.

![](../.gitbook/assets/image%20%2811%29.png)

**Request digital signature**

For additional security of your payments, we perform mandatory verification of the digital signature when creating a payment. The signature guarantees protection against the substitution of the transmitted values \(e.g., changing the payment amount or order number\).

![](../.gitbook/assets/image%20%289%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left"><b>Value</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>signature</b>
      </td>
      <td style="text-align:left">line</td>
      <td style="text-align:left">
        <p>Digital signature. It is formed as sha256( account + &quot;{up}&quot;
          + currency + &quot;{up}&quot; + desc + &quot;{up}&quot; + sum + &quot;{up}&quot;
          + secretKey),
          <br />where <b>sha256</b> is the hashing method;
          <br /> <b>{up}</b> is the parameter separator in the hash function;
          <br /> <b>account, sum, currency, desc</b> are the payment initialization parameters
          described above;
          <br /> <b>secretKey</b> is the secret key of the project (available in your personal
          account);</p>
        <p><b>Important Note</b>. If you do not transmit <b>currency</b> to the payment
          form, this parameter should not be used in signature generation.</p>
      </td>
    </tr>
  </tbody>
</table>

Example of creating a digital signature in PHP:

![](../.gitbook/assets/image%20%2830%29.png)

**Default payment method**

You can define the payment system that will be used for the user by default. To do this, add parameter / **system\_code** corresponding to the [alphabetic code of the payment system](../book-of-reference/payment-system-codes.md) at the end of the URL of your payment form \(for example: [https://unitpay.money/pay/demo\](https://unitpay.money/pay/demo\)\).

**Return to the store's website**

After initializing the payment, the user goes to the receipt page where the payment status is tracked. After users have received a successful or error status, they are redirected to the partner's site \(Fail URL/Success URL fields in the personal account settings\) with GET parameters:

|  | **Value** | **Description** |
| :--- | :--- | :--- |
| account | text | Subscriber ID in the partner's system \(for example, the subscriber's login or email\) |
| paymentId | number | Payment number in the UnitPay system |

