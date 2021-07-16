# Создание платежа \(простой способ\)

{% api-method method="get" host="https://unitpay.money" path="/pay/PUBLIC-KEY?sum&account&desc&signature" %}
{% api-method-summary %}
Создание платежа
{% endapi-method-summary %}

{% api-method-description %}
Для инициализации платежа посредством единой формы оплаты вам достаточно направить пользователя по специальному URL и передать ряд обязательных для оплаты параметров.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="sum" type="number" required=true %}
Сумма платежа. По умолчанию в рублях. См. дополнительный параметр currency.
{% endapi-method-parameter %}

{% api-method-parameter name="account" type="string" required=true %}
Идентификатор абонента в вашей системе \(например email или номер заказа\).
{% endapi-method-parameter %}

{% api-method-parameter name="desc" type="string" required=true %}
Описание заказа. Используется только для информирования при совершении платежа.
{% endapi-method-parameter %}

{% api-method-parameter name="signature" type="string" required=true %}
Цифровая подпись запроса. Она защищает вас от злоумышленников - подмены описания или стоимости заказа, размещения ссылки на оплату на ресурсах мошенников.   
Образуется как sha256\( account + "{up}" + currency + "{up}" + desc + "{up}" + sum + "{up}" + secretKey\),    
где sha256 - метод хеширования;    
"{up}" - разделитель параметров в хеш-функции;    
secretKey - секретный ключ проекта \(доступен в личном кабинете\);    
  
**Важно**. Если вы не передаете currency на форму оплаты, то этот параметр не должен участвовать в формировании подписи.
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="string" required=false %}
Валюта заказа по стандарту ISO 4217 \(RUB, UAH, BYN, EUR, USD итд. Полный список валют https://help.unitpay.money/book-of-reference/currency-codes\).   
Если платежная система не поддерживает требуемую валюту, то сумма будет сконвертирована в валюту системы оплаты.
{% endapi-method-parameter %}

{% api-method-parameter name="locale" type="string" required=false %}
Принудительное указание языка платежной формы, допустимые значения: ru, en. По умолчанию язык формы определяется исходя из страны, к которой относится IP адрес пользователя.
{% endapi-method-parameter %}

{% api-method-parameter name="backUrl" type="string" required=false %}
Адрес возврата пользователя с платежной формы без совершения покупки, по умолчанию используется адрес проекта. В адресе обязательно должен использоваться домен проекта.   
Примеры:`https://redirect.<домен проекта>/?someParams` `https://<домен проекта>/redirect/`
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
В результате выполнения запроса откроется форма оплаты.
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Функциональность онлайн-касс доступна Юридическим лицам РФ и ИП. Подробнее [тут](https://help.unitpay.ru/).
{% endhint %}

**Пример**: 

```http
https://unitpay.money/pay/111111-11111?sum=100&account=222111&desc=Online%20course&signature=2c38bb3114b2f02222ee35f6b60c6bbe628ad31bed59633787204ae59659a02e
```

  
   Значение PUBLIC KEY и SECRET KEY проекта можно найти на странице **Настройки** проекта![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5ec57700042863474d1b1775/file-hpo6F5M6aW.png)

**Пример формирования цифровой подписи:**

{% tabs %}
{% tab title="PHP" %}
```php
function getFormSignature($account, $currency, $desc, $sum, $secretKey) {
    $hashStr = $account.'{up}'.$currency.'{up}'.$desc.'{up}'.$sum.'{up}'.$secretKey;
    return hash('sha256', $hashStr);
}
```
{% endtab %}

{% tab title="Perl" %}
```perl
sub getSignature {
    my ($method, $params, $secretKey) = @_;
    delete $params->{sign};
    delete $params->{signature};
    my $s = $method;
    foreach my $key (sort keys %{$params}) {
        $s .= '{up}' . $params->{$key};
    }
    $s .= '{up}' . $secretKey;
    use Digest::SHA qw(sha256_hex);
    return sha256_hex($s);
}
```
{% endtab %}
{% endtabs %}

#### Метод оплаты по умолчанию

Вы можете определить платежную систему, которая будет использоваться по умолчанию для пользователя. Для этого в конец URL вашей платежной формы \(к примеру [https://unitpay.money/pay/demo](https://unitpay.money/pay/demo)\) добавьте параметр / **код\_системы**, соответствующий буквенному [коду платежной системы](../book-of-reference/payment-system-codes.md).

#### Возврат на сайт магазина

После инициализации оплаты пользователь переходит на страницу чека, где отслеживается статус платежа. При получении успешного либо ошибочного статуса пользователь переходит на сайт партнера по кнопке "В магазин" \(поля Fail URL/Success URL в настройках личного кабинета\) с GET параметрами:

|  | Значение | Описание |
| :--- | :--- | :--- |
| account | текст | Идентификатор абонента в системе партнера \(например, логин или email абонента\) |
| paymentId | число | Номер платежа в системе UnitPay |

Если необходимо принудительно редиректить пользователей сразу после успешной оплаты, то воспользуйтесь параметром **resultUrl из** запроса [на создание платежа](https://help.unitpay.money/payments/create-payment)

{% hint style="info" %}
Если ваш сайт создан с помощью CMS, ознакомьтесь со списком [готовых модулей](../modules/).
{% endhint %}

