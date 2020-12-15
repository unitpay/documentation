# Payment Handler

As the payment is made, we notify the store's platform of the payment status by consistently sending GET requests to the handler's URL.

![](../.gitbook/assets/image%20%2858%29.png)

{% hint style="danger" %}
The domain in the payment handler must completely match the one you add to our system as a project
{% endhint %}

**CHECK:** checking the possibility of providing the service to the subscriber, the request is sent before the payment is made. You must confirm that the system is ready \(check whether the payment amount is correct, whether the account exists in the database, etc.\)

**PAY:** notification of successful debiting, you must provide the service to the subscriber. If any error occurs at this stage \(e.g., the database is inaccessible\), the payment gets the "not completed" status. After the problem is resolved, you can repeat the payment in the statistics interface. Money is credited to the partner's balance regardless of the handler's response

**PREAUTH**: notification in case of payments with pre-authorization when funds are successfully blocked. **Important Note**! You should not provide the service or give the goods to the payer upon receipt of such notification. The funds should be debited and services should be provided when confirmPayment is completed

**ERROR:** payment error at any stage. If an error is caused by an empty/error response from the partner server, the request will not be sent. Please note that this status is not final and there may be situations when the ERROR request may be followed by a PAY request

```text
http://your_payment_handler_address?

     method=check 
     params[account]=userId 
     params[date]=2012-10-01 12:32:00 
     params[operator]=beeline 
     params[paymentType]=mc 
     params[projectId]=1 
     params[phone]=9XXXXXXXXX 
     params[payerSum]=10.00 
     params[payerCurrency]=RUB 
     params[signature]=9bdf52a4830779a1383ac24f1b3ed054 
     params[orderSum]=10.00 
     params[orderCurrency]=RUB 
     params[unitpayId]=1234567 
     params[test]=0
```

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
      <td style="text-align:left"><b>method</b>
      </td>
      <td style="text-align:left">line</td>
      <td style="text-align:left">check &#x2014; request to check the subscriber&apos;s status
        <br />pay &#x2014; notification of debiting
        <br />error &#x2014; error notification</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>unitpayId</b>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Internal payment number in UnitPay</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>projectId</b>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Project ID in UnitPay</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>account</b>
      </td>
      <td style="text-align:left">line</td>
      <td style="text-align:left">Subscriber ID in the partner&apos;s system</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>payerSum</b>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Amount debited from the subscriber&apos;s account</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>payerCurrency</b>
      </td>
      <td style="text-align:left">line</td>
      <td style="text-align:left">Currency of debiting from the subscriber&apos;s account according to ISO
        4217 standard (RUB, UAH, BYN, EUR, USD)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>profit</b>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Your income from this payment, rubles</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>phone</b>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Payer&apos;s phone number (transmitted only for mobile payments)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>paymentType</b>
      </td>
      <td style="text-align:left">line</td>
      <td style="text-align:left"><a href="../book-of-reference/payment-system-codes.md">Payment system code</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>orderSum</b>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Order amount. <b>Make sure to check the received value against the original order amount</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>orderCurrency</b>
      </td>
      <td style="text-align:left">line</td>
      <td style="text-align:left">Order currency according to ISO 4217 (RUB, UAH, BYN, EUR, USD). <b>Make sure to check the received value with the original order currency</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>operator</b>
      </td>
      <td style="text-align:left">line</td>
      <td style="text-align:left"><a href="../book-of-reference/operator-codes.md">Operator alphabetic code</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>date</b>
      </td>
      <td style="text-align:left">line</td>
      <td style="text-align:left">Payment date in the YYYY-mm-dd HH:ii:ss format (for example, 2012-10-01
        12:32:00)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>errorMessage</b>
      </td>
      <td style="text-align:left">line</td>
      <td style="text-align:left">Error details (only for the error method)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>test</b>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Sign of test mode: if a request is made using the test request mechanism,
        the value will equal to 1. For real payments, the value is always 0</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>3ds</b>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Sign of 3-DS for card transaction, the flag is present for PAY notifications</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>subscriptionId</b>
      </td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Subscription ID, it returns after successful payment of the setup fee
        under the subscription. It is present for PAY notifications</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>signature</b>
      </td>
      <td style="text-align:left">line</td>
      <td style="text-align:left">
        <p>Digital signature. It is generated as sha256(method + &quot;{up}&quot;
          + params + &quot;{up}&quot; + secretKey),
          <br />where <b>sha256</b> is the encryption method;
          <br /><b>&quot;{up}&quot;</b> is the parameter separator in the hash function;
          <br
          /><b>method</b> is the request type (check, pay, error);
          <br /><b>params</b> are the values of the parameter from the params arra, combined
          with the &quot;{up}&quot; separator. All parameters must be pre-sorted
          by key; the sign and signature parameters do not participate in merging;
          <br
          /><b>secretKey</b> is the project secret key (available in your personal
          account);</p>
        <p>Example of computing the signature for the request <a href="http://partnerurl/?method=check%20&amp;%20params%5bb%5d=bob&amp;params%5bc%5d=sam&amp;params%5ba%5d=tod"><b>http://partnerUrl?method=check &amp; params[b]=bob &amp; params[c]=sam &amp; params[a]=tod</b></a> and
          secret key <b>&quot;a1b1c1d1&quot;</b>
        </p>
        <p><b>sha256</b>(&quot;check{up}tod{up}bob{up}sam{up}a1b1c1d1&quot;)</p>
      </td>
    </tr>
  </tbody>
</table>

Always check the [IP addresses]() from which requests are sent to your handler

**IMPORTANT NOTE:** the partner's system cannot have two different payments with the same unitpayId. If you receive a repeated CHECK or PAY request, you must return the result of the previous request without depositing/crediting anything

**Successful response**

![](../.gitbook/assets/image%20%2816%29.png)

| Запрос успешно обработан | Request processed successfully |
| :--- | :--- |


|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | Text status of query progress. |

**Error response**

![](../.gitbook/assets/image%20%2863%29.png)

| Описание ошибки | Error description |
| :--- | :--- |


|  | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | Information with a description of the payment generation error. |

In case of errors, the text from the "message" parameter will be shown to the client when using the payment form

**IMPORTANT NOTE**: If any error occurs at the PAY stage \(e.g., the database can not be accessed\), the payment gets the "not completed" status. After the problem is resolved, repeat the payment in the statistics.

