# Drupal 8, 9 \(commerce\)

### Инструкция по настройке и установке модуля.

{% hint style="info" %}
Модуль поддерживает работу с 8 и 9 версией Drupal \(commerce\)
{% endhint %}

1. Скачайте  [архив](https://github.com/unitpay/drupal/archive/main.zip) с модулем.

2. Установите модуль. Для этого перейдите в Extend -&gt; Install new module. Выбираете архив с модулем и далее "Сохранить".

![](../../.gitbook/assets/d_ustanovka.png)

3. Перейдите в Commerce -&gt; Configuration -&gt; Payment gateway. PAYMENT GATEWAY: "Unitpay" Нажмите "Edit".В поле DOMAIN вставьте значение unitpay.money, в поля PUBLIC KEY и SECRET KEY скопируйте публичный и секретный ключ из личного кабинета Unitpay.

![](../../.gitbook/assets/8-nastroiki1.png)

4. Включите модуль и сохраните.

![](../../.gitbook/assets/8-nastroiki2.png)

5. В личном кабинете Unitpay добавьте адрес обработчика в формате **http://&lt;имя вашего сайта&gt;/commerce-unitpay/callback**

![](../../.gitbook/assets/213514da544a8913f88105cb2135f9ae.png)

7. Валюта задается в двух местах. Commerce -&gt; Configuration -&gt; Currencies

![](../../.gitbook/assets/3090bece182e7d76cda5a2aba84eb2ec.png)

8. И далее, чтобы появилась возможность менять в товарах, нужно добавить в "Product types". Commerce -&gt; Configuration -&gt; Product types -&gt; Edit Default -&gt; Manage fields

![](../../.gitbook/assets/1111.png)

![](../../.gitbook/assets/222.png)

![](../../.gitbook/assets/3333.png)

![](../../.gitbook/assets/4444.png)

9. Аналогично требуется проделать для "variation types". Commerce -&gt; Configuration -&gt; Product variation types -&gt; Edit Default -&gt; Manage fields



