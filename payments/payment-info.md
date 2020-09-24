# Информация о платеже

{% api-method method="get" host="https://unitpay.money/api" path="?method=getPayment&params\[paymentId\]=153091501&params\[secretKey\]=x6bh0qbewehfppogkz6lufartkzyv7o0" %}
{% api-method-summary %}
Получение информации о платеже
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="paymentId" type="integer" required=true %}
ID платежа в системе UnitPay  
Например: 153091501
{% endapi-method-parameter %}

{% api-method-parameter name="secretKey" type="string" required=true %}
Секретный ключ проекта, доступен в настройках проекта
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
   "result": {
      "paymentId": 153091501,
      "status": "success",
      "paymentType": "card",
      "date": "2020-02-16 09:22:22",
      "purse": "546946xxxxxx0236",
      "account": "demo",
      "profit": "9.80",
      "projectId": 135,
      "orderSum": "10.00",
      "orderCurrency": "RUB",
      "payerSum": "10.00",
      "payerCurrency": "RUB",
      "availableForRefund": "10.00",
      "isPreauth": 0,
      "refunds": [],
      "receiptUrl": "https://consumer.1-ofd.ru/v1?fn=9282000100367629&fp=2120704629&i=101164&t=20200216T092200&s=26&n=1"
   }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

**Параметры успешного ответа:**

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x41D;&#x430;&#x437;&#x432;&#x430;&#x43D;&#x438;&#x435;</th>
      <th style="text-align:left">&#x422;&#x438;&#x43F;</th>
      <th style="text-align:left">&#x41E;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x435;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>status</b>
      </td>
      <td style="text-align:left">&#x441;&#x442;&#x440;&#x43E;&#x43A;&#x430;</td>
      <td style="text-align:left">success &#x2014; &#x443;&#x441;&#x43F;&#x435;&#x448;&#x43D;&#x44B;&#x439;
        &#x43F;&#x43B;&#x430;&#x442;&#x435;&#x436;;
        <br />wait &#x2014; &#x43E;&#x436;&#x438;&#x434;&#x430;&#x43D;&#x438;&#x435;
        &#x43E;&#x43F;&#x43B;&#x430;&#x442;&#x44B;;
        <br />error &#x2014; &#x43E;&#x448;&#x438;&#x431;&#x43A;&#x430; &#x43F;&#x43B;&#x430;&#x442;&#x435;&#x436;&#x430;;
        <br
        />error_pay &#x2014; &#x43E;&#x448;&#x438;&#x431;&#x43A;&#x430;/&#x43E;&#x442;&#x43A;&#x430;&#x437;
        &#x43C;&#x430;&#x433;&#x430;&#x437;&#x438;&#x43D;&#x430; &#x43D;&#x430;
        &#x441;&#x442;&#x430;&#x434;&#x438;&#x438; PAY, &#x432; &#x441;&#x442;&#x430;&#x442;&#x438;&#x441;&#x442;&#x438;&#x43A;&#x435;
        &#x43A;&#x430;&#x43A; &quot;&#x43D;&#x435;&#x437;&#x430;&#x432;&#x435;&#x440;&#x448;&#x435;&#x43D;&quot;;
        <br
        />error_check &#x2014; &#x43E;&#x448;&#x438;&#x431;&#x43A;&#x430;/&#x43E;&#x442;&#x43A;&#x430;&#x437;
        &#x43C;&#x430;&#x433;&#x430;&#x437;&#x438;&#x43D;&#x430; &#x43D;&#x430;
        &#x441;&#x442;&#x430;&#x434;&#x438;&#x438; CHECK, &#x432; &#x441;&#x442;&#x430;&#x442;&#x438;&#x441;&#x442;&#x438;&#x43A;&#x435;
        &#x43A;&#x430;&#x43A; &quot;&#x43E;&#x442;&#x43A;&#x43B;&#x43E;&#x43D;&#x435;&#x43D;&quot;;
        <br
        />refund &#x2014; &#x432;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x442; &#x441;&#x440;&#x435;&#x434;&#x441;&#x442;&#x432;
        &#x43F;&#x43E;&#x43A;&#x443;&#x43F;&#x430;&#x442;&#x435;&#x43B;&#x44E;;
        <br
        />secure &#x2014; &#x43D;&#x430; &#x43F;&#x440;&#x43E;&#x432;&#x435;&#x440;&#x43A;&#x435;
        &#x443; &#x441;&#x43B;&#x443;&#x436;&#x431;&#x44B; &#x431;&#x435;&#x437;&#x43E;&#x43F;&#x430;&#x441;&#x43D;&#x43E;&#x441;&#x442;&#x438;
        &#x431;&#x430;&#x43D;&#x43A;&#x430;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>paymentId</b> 
      </td>
      <td style="text-align:left">&#x447;&#x438;&#x441;&#x43B;&#x43E;</td>
      <td style="text-align:left">ID &#x43F;&#x43B;&#x430;&#x442;&#x435;&#x436;&#x430; &#x432; &#x441;&#x438;&#x441;&#x442;&#x435;&#x43C;&#x435;
        UnitPay</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>projectId</b> 
      </td>
      <td style="text-align:left">&#x447;&#x438;&#x441;&#x43B;&#x43E;</td>
      <td style="text-align:left">ID &#x43F;&#x440;&#x43E;&#x435;&#x43A;&#x442;&#x430; &#x432; &#x441;&#x438;&#x441;&#x442;&#x435;&#x43C;&#x435;
        UnitPay</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>account</b> 
      </td>
      <td style="text-align:left">&#x441;&#x442;&#x440;&#x43E;&#x43A;&#x430;</td>
      <td style="text-align:left">&#x418;&#x434;&#x435;&#x43D;&#x442;&#x438;&#x444;&#x438;&#x43A;&#x430;&#x442;&#x43E;&#x440;
        &#x43A;&#x43B;&#x438;&#x435;&#x43D;&#x442;&#x430; (&#x438;&#x43B;&#x438;
        &#x437;&#x430;&#x43A;&#x430;&#x437;&#x430;) &#x432; &#x441;&#x438;&#x441;&#x442;&#x435;&#x43C;&#x435;
        &#x43F;&#x430;&#x440;&#x442;&#x43D;&#x435;&#x440;&#x430;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>purse</b> 
      </td>
      <td style="text-align:left">&#x441;&#x442;&#x440;&#x43E;&#x43A;&#x430;</td>
      <td style="text-align:left">&#x41A;&#x43E;&#x448;&#x435;&#x43B;&#x435;&#x43A; (&#x43D;&#x43E;&#x43C;&#x435;&#x440;
        &#x441;&#x447;&#x435;&#x442;&#x430;) &#x441; &#x43A;&#x43E;&#x442;&#x43E;&#x440;&#x43E;&#x433;&#x43E;
        &#x43F;&#x440;&#x43E;&#x438;&#x437;&#x432;&#x43E;&#x434;&#x438;&#x43B;&#x430;&#x441;&#x44C;
        &#x43E;&#x43F;&#x43B;&#x430;&#x442;&#x430;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>profit</b>
      </td>
      <td style="text-align:left">&#x447;&#x438;&#x441;&#x43B;&#x43E;</td>
      <td style="text-align:left">&#x412;&#x430;&#x448; &#x434;&#x43E;&#x445;&#x43E;&#x434; &#x441; &#x434;&#x430;&#x43D;&#x43D;&#x43E;&#x433;&#x43E;
        &#x43F;&#x43B;&#x430;&#x442;&#x435;&#x436;&#x430;, &#x432; &#x440;&#x443;&#x431;&#x43B;&#x44F;&#x445;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>paymentType</b>
      </td>
      <td style="text-align:left">&#x441;&#x442;&#x440;&#x43E;&#x43A;&#x430;</td>
      <td style="text-align:left"><a href="../book-of-reference/payment-system-codes.md">&#x41A;&#x43E;&#x434; &#x43F;&#x43B;&#x430;&#x442;&#x435;&#x436;&#x43D;&#x43E;&#x439; &#x441;&#x438;&#x441;&#x442;&#x435;&#x43C;&#x44B;</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>orderSum</b>
      </td>
      <td style="text-align:left">&#x447;&#x438;&#x441;&#x43B;&#x43E;</td>
      <td style="text-align:left">&#x421;&#x443;&#x43C;&#x43C;&#x430; &#x437;&#x430;&#x43A;&#x430;&#x437;&#x430;.
        &#x41E;&#x431;&#x44F;&#x437;&#x430;&#x442;&#x435;&#x43B;&#x44C;&#x43D;&#x43E;
        &#x441;&#x432;&#x435;&#x440;&#x44F;&#x439;&#x442;&#x435; &#x434;&#x430;&#x43D;&#x43D;&#x43E;&#x435;
        &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435; &#x441; &#x43E;&#x440;&#x438;&#x433;&#x438;&#x43D;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;&#x439;
        &#x441;&#x443;&#x43C;&#x43C;&#x43E;&#x439; &#x437;&#x430;&#x43A;&#x430;&#x437;&#x430;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>orderCurrency</b>
      </td>
      <td style="text-align:left">&#x441;&#x442;&#x440;&#x43E;&#x43A;&#x430;</td>
      <td style="text-align:left">&#x412;&#x430;&#x43B;&#x44E;&#x442;&#x430; &#x437;&#x430;&#x43A;&#x430;&#x437;&#x430;
        (RUB, UAH, BYN, EUR, USD). &#x41E;&#x431;&#x44F;&#x437;&#x430;&#x442;&#x435;&#x43B;&#x44C;&#x43D;&#x43E;
        &#x441;&#x432;&#x435;&#x440;&#x44F;&#x439;&#x442;&#x435; &#x434;&#x430;&#x43D;&#x43D;&#x43E;&#x435;
        &#x437;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435; &#x441; &#x43E;&#x440;&#x438;&#x433;&#x438;&#x43D;&#x430;&#x43B;&#x44C;&#x43D;&#x43E;&#x439;
        &#x432;&#x430;&#x43B;&#x44E;&#x442;&#x43E;&#x439; &#x437;&#x430;&#x43A;&#x430;&#x437;&#x430;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>date</b>
      </td>
      <td style="text-align:left">&#x441;&#x442;&#x440;&#x43E;&#x43A;&#x430;</td>
      <td style="text-align:left">&#x414;&#x430;&#x442;&#x430; &#x43F;&#x43B;&#x430;&#x442;&#x435;&#x436;&#x430;
        &#x432; &#x444;&#x43E;&#x440;&#x43C;&#x430;&#x442;&#x435; YYYY-mm-dd HH:ii:ss
        (&#x43D;&#x430;&#x43F;&#x440;&#x438;&#x43C;&#x435;&#x440; 2012-10-01 12:32:00)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>payerSum</b>
      </td>
      <td style="text-align:left">&#x447;&#x438;&#x441;&#x43B;&#x43E;</td>
      <td style="text-align:left">&#x421;&#x443;&#x43C;&#x43C;&#x430; &#x441;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x44F;
        &#x441; &#x43B;&#x438;&#x446;&#x435;&#x432;&#x43E;&#x433;&#x43E; &#x441;&#x447;&#x435;&#x442;&#x430;
        &#x430;&#x431;&#x43E;&#x43D;&#x435;&#x43D;&#x442;&#x430;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>payerCurrency</b>
      </td>
      <td style="text-align:left">&#x441;&#x442;&#x440;&#x43E;&#x43A;&#x430;</td>
      <td style="text-align:left">&#x412;&#x430;&#x43B;&#x44E;&#x442;&#x430; &#x441;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x44F;
        &#x441; &#x43B;&#x438;&#x446;&#x435;&#x432;&#x43E;&#x433;&#x43E; &#x441;&#x447;&#x435;&#x442;&#x430;
        &#x430;&#x431;&#x43E;&#x43D;&#x435;&#x43D;&#x442;&#x430; &#x43F;&#x43E;
        &#x441;&#x442;&#x430;&#x43D;&#x434;&#x430;&#x440;&#x442;&#x443; ISO 4217
        (RUB, UAH, BYN, EUR, USD)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>receiptUrl</b>
      </td>
      <td style="text-align:left">&#x441;&#x442;&#x440;&#x43E;&#x43A;&#x430;</td>
      <td style="text-align:left">
        <p>&#x421;&#x441;&#x44B;&#x43B;&#x43A;&#x430; &#x43D;&#x430; &#x447;&#x435;&#x43A;.</p>
        <p><code>&#x41F;&#x440;&#x438;&#x43C;&#x435;&#x447;&#x430;&#x43D;&#x438;&#x435;: &#x432;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442;&#x441;&#x44F;, &#x435;&#x441;&#x43B;&#x438; &#x43F;&#x43E;&#x434;&#x43A;&#x43B;&#x44E;&#x447;&#x435;&#x43D;&#x430; &#x43A;&#x430;&#x441;&#x441;&#x430; &#x42E;&#x43D;&#x438;&#x442;.&#x427;&#x435;&#x43A;&#x438;, &#x410;&#x442;&#x43E;&#x43B; &#x438;&#x43B;&#x438; e-comm.</code>
        </p>
        <p>&#x41D;&#x430;&#x43F;&#x440;&#x438;&#x43C;&#x435;&#x440;: <a href="https://consumer.1-ofd.ru/v1?fn=9282000100367629&amp;fp=2120704629&amp;i=101164&amp;t=20200216T092200&amp;s=26&amp;n=1">https://consumer.1-ofd.ru/v1?fn=9282000100367629&amp;fp=2120704629&amp;i=101164&amp;t=20200216T092200&amp;s=26&amp;n=1</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>errorMessage</b>
      </td>
      <td style="text-align:left">&#x441;&#x442;&#x440;&#x43E;&#x43A;&#x430;</td>
      <td style="text-align:left">&#x414;&#x435;&#x442;&#x430;&#x43B;&#x438;&#x437;&#x430;&#x446;&#x438;&#x44F;
        &#x43E;&#x448;&#x438;&#x431;&#x43A;&#x438; (&#x442;&#x43E;&#x43B;&#x44C;&#x43A;&#x43E;
        &#x434;&#x43B;&#x44F; &#x441;&#x442;&#x430;&#x442;&#x443;&#x441;&#x430;
        error)</td>
    </tr>
  </tbody>
</table>



#### Параметры неуспешного ответа

|  | Значение | Описание |
| :--- | :--- | :--- |
| **message** | строка | Информация с описанием ошибки запроса. |

{% hint style="warning" %}
Запрос можно выполнить в тестовом режиме. [Узнать подробнее](../other/test-api.md)
{% endhint %}

