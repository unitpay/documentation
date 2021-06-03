# Создание платежа



```http
https://unitpay.money/api?
     method=initPayment 
     params[paymentType]=yandex 
     params[account]=order413 
     params[sum]=10.00 
     params[projectId]=1 
     params[resultUrl]=http://вашсайт.ru  
     params[ip]=77.129.27.24 
     params[secretKey]=ключ 
     params[signature]=цифровая подпись 
     params[preauth]=1 
     params[customerEmail]=Email плательщика
```

**Обязательные параметры:**

|  | Значение | Описание |
| :--- | :--- | :--- |
| **paymentType** | строка | [Код платежной системы](../book-of-reference/payment-system-codes.md), через которую будет идти оплата |
| **account**   | строка | Идентификатор абонента в системе партнера \(например, логин или email абонента\) |
| **sum** | число | Сумма платежа в рублях \(например, 10.00\) |
| **projectId** | число | ID вашего проекта в системе UnitPay |
| **resultUrl** | строка | Urlencoded адрес перехода пользователя после оплаты \(например, [http://вашсайт.ru](http://unitpay.ru/)\). Если параметр не задан, то будет использован адрес страницы чека платежа. |
| **desc** | строка | Описание заказа |
| **ip** | строка | IP адрес плательщика |
| **secretKey** | строка | Секретный ключ, доступен в настройках проекта    |

#### 

**Параметры в зависимости от типа оплаты:**

|  | Значение | Описание |
| :--- | :--- | :--- |
| phone | число | Телефон с кодом страны \(например, 79520000000\) |
| operator | строка | Буквенный [код оператора](../book-of-reference/operator-codes.md) для SMS-биллинга. Для остальных систем оператор определяется автоматически |

  
   Значение PUBLIC KEY и SECRET KEY проекта можно найти на странице **Настройки** проекта![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5ec57700042863474d1b1775/file-hpo6F5M6aW.png)

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

**Дополнительные параметры оплаты:**

|  | Значение | Описание |
| :--- | :--- | :--- |
| **currency** | строка | Валюта заказа по стандарту ISO 4217 \(RUB, UAH, BYN, EUR, USD итд. [Полный список валют](https://help.unitpay.money/book-of-reference/bukvennye-kody-valyut)\). Если платежная система не поддерживает требуемую валюту, то сумма будет сконвертирована в валюту системы оплаты |
| **locale** | строка | Принудительное указание языка платежной формы, допустимые значения: ru, en. По умолчанию язык формы определяется исходя из страны, к которой относится IP адрес пользователя |
| **signature** | строка | Цифровая подпись запроса. Данная функция является обязательной у всех новых партнёров Unitpay. Они защищает вас от злоумышленников - подмены описания или стоимости заказа, размещения ссылки на оплату на ресурсах мошенников. |
| **backUrl** | строка | Адрес возврата пользователя с платежной формы без совершения покупки, по умолчанию используется адрес проекта. В адресе обязательно должен использоваться домен проекта. Примеры: "https://redirect.&lt;домен проекта&gt;/?someParams", "https://&lt;домен проекта&gt;/redirect/" |
| **subscription** | true/false | Используйте данный флаг, если требуется создать подписку по карте плательщика. Идентификатор подписки \(subscriptionId\) будет передан в методе PAY на ваш обработчик платежа. Использование подписок возможно только после согласования с вашим курирующим менеджером |
| **subscriptionId** | число | Идентификатор подписки, по которой требуется произвести списание средств. Данный параметр должен быть предварительно получен в методе PAY на ваш обработчик платежа  |
| **preauth** | true/false | Используйте этот флаг для создания платежа с преавторизацией, по умолчанию флаг выключен и значение равно 0 |
| **preauthExpireLogic** | число | Поле для логики блокировки платежей с преавторизацией     0 - При отсутствии запроса на подтверждение или отмену, платеж по истечении срока блокировки на стороне банка-эквайера \(~114 часов после создания платежа\) будет подтвержден  1 - При отсутствии запроса на подтверждение или отмену, платеж по истечении срока блокировки на стороне банка-эквайера \(~114 часов после создания платежа\) будет отменен.   Если параметр не будет использован, платеж будет отменен по истечении срока.   |

{% hint style="warning" %}
Запрос можно выполнить в тестовом режиме. [Узнать подробнее](../other/test-api.md)
{% endhint %}

{% hint style="info" %}
По мере выполнения платежа мы уведомляем платформу магазина о статусе оплаты, последовательно [отправляя GET запросы на URL обработчика](https://help.unitpay.money/payments/payment-handler).
{% endhint %}

#### Успешный ответ

{% tabs %}
{% tab title="Redirect" %}
```text
{
  "result": {
    "message": "Платеж успешно создан.",
    "paymentId": "1400072",
    "receiptUrl": "https://unitpay.money/pay/receipt/111-ab34c22",
    "type": "redirect",
    "redirectUrl": "http://unitpay.ru/pay/redirect/111-ab34c22" 
  }
}
```
{% endtab %}

{% tab title="Response \(не ApplePay\)" %}
```text
{
  "result": {
    "message": "Платеж успешно создан.",
    "paymentId": "1400072",
    "receiptUrl": "https://unitpay.money/pay/receipt/111-ab34c22",
    "type": "response",
    "response": "<form>...</form>" 
  }
}
```
{% endtab %}

{% tab title="Response \(ApplePay\)" %}
```
{
  "result": {
    "message": "Платеж успешно создан.",
    "paymentId": "1400072",
    "receiptUrl": "https://unitpay.money/pay/receipt/111-ab34c22",
    "type": "response",
    "response": {
      "success": 1,
      "orderId": "123",
      "appleResponse": {
        /*объект*/
      },
      "approveUrl": "url"
    }
  }
}

```
{% endtab %}

{% tab title="Invoice" %}
```
{
  "result": {
    "message": "Платеж успешно создан.",
    "paymentId": "1400072",
    "receiptUrl": "https://unitpay.money/pay/receipt/111-ab34c22",
    "type": "invoice",
    "invoiceId": "123" 
  }
}
```
{% endtab %}
{% endtabs %}

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left">&#x417;&#x43D;&#x430;&#x447;&#x435;&#x43D;&#x438;&#x435;</th>
      <th style="text-align:left">&#x41E;&#x43F;&#x438;&#x441;&#x430;&#x43D;&#x438;&#x435;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>message</b>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x418;&#x43D;&#x444;&#x43E;&#x440;&#x43C;&#x430;&#x446;&#x438;&#x44F;
        &#x43E; &#x440;&#x435;&#x437;&#x443;&#x43B;&#x44C;&#x442;&#x430;&#x442;&#x435;
        &#x444;&#x43E;&#x440;&#x43C;&#x438;&#x440;&#x43E;&#x432;&#x430;&#x43D;&#x438;&#x44F;
        &#x43F;&#x43B;&#x430;&#x442;&#x435;&#x436;&#x430;</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>paymentId</b>
      </td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">&#x41D;&#x43E;&#x43C;&#x435;&#x440; &#x43F;&#x43B;&#x430;&#x442;&#x435;&#x436;&#x430;
        &#x432; &#x441;&#x438;&#x441;&#x442;&#x435;&#x43C;&#x435; UnitPay</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>receiptUrl</b>
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x421;&#x441;&#x44B;&#x43B;&#x43A;&#x430; &#x43D;&#x430; &#x447;&#x435;&#x43A; <code>&#x41F;&#x440;&#x438;&#x43C;&#x435;&#x447;&#x430;&#x43D;&#x438;&#x435;: &#x432;&#x43E;&#x437;&#x432;&#x440;&#x430;&#x449;&#x430;&#x435;&#x442;&#x441;&#x44F;, &#x435;&#x441;&#x43B;&#x438; &#x43F;&#x43E;&#x434;&#x43A;&#x43B;&#x44E;&#x447;&#x435;&#x43D;&#x430; &#x43A;&#x430;&#x441;&#x441;&#x430; &#x42E;&#x43D;&#x438;&#x442;.&#x427;&#x435;&#x43A;&#x438;, &#x410;&#x442;&#x43E;&#x43B; &#x438;&#x43B;&#x438; e-comm.</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>type</b> 
      </td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p><b>&#x422;&#x438;&#x43F; &#x43E;&#x442;&#x432;&#x435;&#x442;&#x430;:</b>
        </p>
        <p><b>redirect</b> &#x2014; &#x43D;&#x435;&#x43E;&#x431;&#x445;&#x43E;&#x434;&#x438;&#x43C;&#x43E;
          &#x43F;&#x435;&#x440;&#x435;&#x43D;&#x430;&#x43F;&#x440;&#x430;&#x432;&#x438;&#x442;&#x44C;
          &#x43F;&#x43E;&#x43B;&#x44C;&#x437;&#x43E;&#x432;&#x430;&#x442;&#x435;&#x43B;&#x44F;
          &#x43D;&#x430; &#x430;&#x434;&#x440;&#x435;&#x441;, &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x44B;&#x435;
          &#x432; <em>redirectUrl</em>
        </p>
        <p><b>response</b> - &#x43D;&#x435;&#x43E;&#x431;&#x445;&#x43E;&#x434;&#x438;&#x43C;&#x43E;
          &#x43F;&#x43E;&#x43A;&#x430;&#x437;&#x430;&#x442;&#x44C; &#x43F;&#x43E;&#x43B;&#x44C;&#x437;&#x43E;&#x432;&#x430;&#x442;&#x435;&#x43B;&#x44E;
          &#x438;&#x43D;&#x444;&#x43E;&#x440;&#x43C;&#x430;&#x446;&#x438;&#x44E;,
          &#x443;&#x43A;&#x430;&#x437;&#x430;&#x43D;&#x43D;&#x443;&#x44E; &#x432; <em>response</em> 
          <br
          /><b>invoice</b> &#x2014; &#x441;&#x447;&#x435;&#x442; &#x441;&#x43E;&#x437;&#x434;&#x430;&#x43D;
          &#x430;&#x432;&#x442;&#x43E;&#x43C;&#x430;&#x442;&#x438;&#x447;&#x435;&#x441;&#x43A;&#x438;
          &#x438; &#x43D;&#x430;&#x43F;&#x440;&#x430;&#x432;&#x43B;&#x435;&#x43D;
          &#x43F;&#x43B;&#x430;&#x442;&#x435;&#x43B;&#x44C;&#x449;&#x438;&#x43A;&#x443;.
          &#x414;&#x43E;&#x43F;&#x43E;&#x43B;&#x43D;&#x438;&#x442;&#x435;&#x43B;&#x44C;&#x43D;&#x44B;&#x445;
          &#x434;&#x435;&#x439;&#x441;&#x442;&#x432;&#x438;&#x439; &#x43D;&#x435;
          &#x442;&#x440;&#x435;&#x431;&#x443;&#x435;&#x442;&#x441;&#x44F;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">redirectUrl</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">URL &#x434;&#x43B;&#x44F; &#x43F;&#x435;&#x440;&#x435;&#x430;&#x434;&#x440;&#x435;&#x441;&#x430;&#x446;&#x438;&#x438;
        &#x43F;&#x43E;&#x43B;&#x44C;&#x437;&#x43E;&#x432;&#x430;&#x442;&#x435;&#x43B;&#x44F;
        &#x43D;&#x430; &#x448;&#x43B;&#x44E;&#x437; &#x43F;&#x43B;&#x430;&#x442;&#x435;&#x436;&#x43D;&#x43E;&#x439;
        &#x43F;&#x43B;&#x430;&#x442;&#x444;&#x43E;&#x440;&#x43C;&#x44B;</td>
    </tr>
    <tr>
      <td style="text-align:left">response</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>html &#x43A;&#x43E;&#x434; &#x444;&#x43E;&#x440;&#x43C;&#x44B;, &#x430;
          &#x435;&#x441;&#x43B;&#x438; ApplePay, &#x442;&#x43E; json</p>
        <p></p>
        <p>html - &#x43D;&#x435;&#x43E;&#x431;&#x445;&#x43E;&#x434;&#x438;&#x43C;&#x43E;
          &#x43E;&#x442;&#x43E;&#x431;&#x440;&#x430;&#x437;&#x438;&#x442;&#x44C;
          &#x43D;&#x430; &#x441;&#x442;&#x440;&#x430;&#x43D;&#x438;&#x446;&#x435;</p>
        <p>json - &#x43D;&#x435;&#x43E;&#x431;&#x445;&#x43E;&#x434;&#x438;&#x43C;&#x43E;
          &#x43D;&#x430;&#x43F;&#x440;&#x430;&#x432;&#x438;&#x442;&#x44C; &#x43F;&#x43E;&#x43B;&#x44C;&#x437;&#x43E;&#x432;&#x430;&#x442;&#x435;&#x43B;&#x44F;
          &#x43F;&#x43E; approveUrl</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">invoiceId</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">id &#x441;&#x447;&#x435;&#x442;&#x430;</td>
    </tr>
  </tbody>
</table>

#### Ошибочный ответ

```text
{"error": {
    "message": "Описание ошибки"
}}
```

|  | Значение | Описание |
| :--- | :--- | :--- |
| **message** | строка | Информация с описанием ошибки формирования платежа |

{% hint style="info" %}
Если ваш сайт создан с помощью CMS, ознакомьтесь со списком [готовых модулей](../modules/).  
Для взаимодействия с API вы можете использовать библиотеку [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk).
{% endhint %}

