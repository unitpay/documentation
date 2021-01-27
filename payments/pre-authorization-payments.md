# Двухстадийные платежи \(платежи с преавторизацией\)

{% api-method method="get" host="https://unitpay.money/api" path="?method=initPayment" %}
{% api-method-summary %}
Инициализация платежа с преавторизацией
{% endapi-method-summary %}

{% api-method-description %}
Для создания платежа с преавторизацией необходимо передать дополнительный параметр **preauth**. Полный набор параметров описан на странице создания платежа.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="preauth" type="integer" required=false %}
Используйте этот флаг для создания платежа с преавторизацией, по умолчанию флаг выключен и значение равно 0, для включения необходимо передать 1.
{% endapi-method-parameter %}

{% api-method-parameter name="preauthExpireLogic" type="integer" required=false %}
Поле для логики блокировки платежей с преавторизацией:  
0 - при отсутствии запроса на подтверждение или отмену, платеж по истечении срока блокировки на стороне банка-эквайера \(~114 часов после создания платежа\) будет подтвержден;  
1 - при отсутствии запроса на подтверждение или отмену, платеж по истечении срока блокировки на стороне банка-эквайера \(~114 часов после создания платежа\) будет отменен.   
  
Если параметр не будет использован, платеж будет отменен по истечении срока.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://unitpay.money/api" path="?method=confirmPayment&params\[paymentId\]=1&params\[secretKey\]=ключ" %}
{% api-method-summary %}
Подтверждение платежа с преавторизацией
{% endapi-method-summary %}

{% api-method-description %}
Для подтверждения платежа с преавторизацией \(списания заблокированных на карте плательщика средств\) необходимо выполнить данный запрос.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="paymentId" type="integer" required=true %}
ID платежа в системе UnitPay.
{% endapi-method-parameter %}

{% api-method-parameter name="secretKey" type="string" required=true %}
Секретный ключ проекта.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

{% tabs %}
{% tab title="Успешный ответ" %}
```text
{ "message": "Блокировка успешно отменёна" }
```
{% endtab %}

{% tab title="Ошибочный ответ" %}
```
{
   "error": {
      "message": "Платеж не может быть подтвержден"
   }
}
```
{% endtab %}
{% endtabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://unitpay.money/api" path="?method=cancelPayment&params\[paymentId\]=1&params\[secretKey\]=ключ" %}
{% api-method-summary %}
Отмена платежа с преавторизацией
{% endapi-method-summary %}

{% api-method-description %}
Для отмены платежа с преавторизацией \(разблокировки средств на карте плательщика\) необходимо выполнить данный запрос.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="secretKey" type="string" required=true %}
Секретный ключ проекта.
{% endapi-method-parameter %}

{% api-method-parameter name="paymentId" type="integer" required=true %}
ID платежа в системе UnitPay.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
Двухстадийные платежи не работают одновременно с [подписками](https://help.unitpay.money/payments/recurring-payments/create-subscription)
{% endhint %}

