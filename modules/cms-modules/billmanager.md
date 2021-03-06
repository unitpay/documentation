# BILLmanager

### Инструкция по настройке приема платежей через сервис BILLmanager.

{% hint style="info" %}
Подробная инструкция и поддерживаемые возможности описаны [в документации BILLmanager](https://docs.ispsystem.ru/billmanager/finansy/podklyuchenie-modulej-oplaty/unitpay#UnitPay-НастройканасторонеBILLmanager)
{% endhint %}

### Настройка на стороне платежной системы <a id="UnitPay-&#x41D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x430;&#x43D;&#x430;&#x441;&#x442;&#x43E;&#x440;&#x43E;&#x43D;&#x435;&#x43F;&#x43B;&#x430;&#x442;&#x435;&#x436;&#x43D;&#x43E;&#x439;&#x441;&#x438;&#x441;&#x442;&#x435;&#x43C;&#x44B;"></a>

На стороне UnitPay необходимо указать настройки:

* **PUBLIC KEY** — Параметр необходим для идентификации получателя платежа. Используется в настройках метода оплаты на стороне BILLmanager.
* **Направить клиента на специальные страницы проекта** — флаг должен быть включен.
* **Success URL** — URL адрес взаимодействия с биллинговой системой для успешных платежей. Необходимо указать URL вида: 'https://&lt;адрес\_BILLmanager&gt;/billmgr?func=payment.success'.
* **Fail URL** — URL адрес взаимодействия с биллинговой системой для неуспешных платежей. Необходимо указать URL вида: 'https://&lt;адрес\_BILLmanager&gt;/billmgr?func=payment.fail'.
* **Обработчик платежей** — URL адрес взаимодействия с биллинговой системой. Необходимо указать URL вида: 'https://&lt;адрес\_BILLmanager&gt;/mancgi/unitpayresult'. 
* **SECRET KEY** — ключ для проверки подписей платежей. Используется в настройках метода оплаты на стороне BILLmanager.

### Настройка на стороне BILLmanager <a id="UnitPay-&#x41D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x430;&#x43D;&#x430;&#x441;&#x442;&#x43E;&#x440;&#x43E;&#x43D;&#x435;BILLmanager"></a>

Подключение модуля оплаты выполняется в разделе **Провайдер** → **Методы оплаты**.  Мастер подключения состоит из трех шагов:

* **Шаг 1. Выбор метода оплаты**. В качестве метода оплаты необходимо выбрать "UnitPay".
* **Шаг 2. Настройка интеграции**. Ввод информации, необходимой для интеграции с платежной системой.
* **Шаг 3. Настройка метода оплаты**. Настройка внутренних \(в пределах BILLmanager\) параметров метода оплаты.

#### Настройка интеграции <a id="UnitPay-&#x41D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x430;&#x438;&#x43D;&#x442;&#x435;&#x433;&#x440;&#x430;&#x446;&#x438;&#x438;"></a>

### [![](https://docs.ispsystem.ru/billmanager/files/16548599/16548601/1/1519229905000/unit.png)](https://docs.ispsystem.ru/billmanager/files/16548599/16548601/1/1519229905000/unit.png) <a id="UnitPay-unit.pngeffects=drop-shadow400"></a>

**PUBLIC KEY** — публичный ключ магазина. Указан в личном кабинете UnitPay в настройках вашего проекта.  
**SECRET KEY** — секретный ключ магазина. Указан в личном кабинете UnitPay в настройках вашего проекта.

