# Закрытие подписки

{% api-method method="get" host="https://unitpay.money/api" path="?method=closeSubscription&params\[subscriptionId\]=1&params\[secretKey\]=ключ" %}
{% api-method-summary %}
Закрытие подписки
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="subscriptionId" type="integer" required=true %}
ID подписки в системе UnitPay
{% endapi-method-parameter %}

{% api-method-parameter name="secretKey" type="string" required=true %}
Секретный ключ, доступен в настройках проекта
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

{% tabs %}
{% tab title="Успешный ответ" %}
```
{
   "result": {
      "message": "Подписка успешно закрыта"
   }
}
```
{% endtab %}

{% tab title="Ошибочный ответ" %}
```
{
   "error": {
      "message": "Описание ошибки"
   }
}
```
{% endtab %}
{% endtabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
Запрос можно выполнить в тестовом режиме. [Узнать подробнее](../../other/test-api.md)
{% endhint %}

