# Joomshopping 4 \(joomla 3\)

### Инструкция по настройке и установке модуля.

1. Скачайте [архив](https://github.com/unitpay/jshopping-module/releases/download/v2.0.1/jshopping-module-2.0.1.zip) с модулем. Модуль тестировался на Joomla 3.9.11 + Joomshopping 4.18.3

2. Зайдите в админпанель сайта.

3. Установите модуль. Для этого перейдите в Компоненты-&gt; Joomshopping-&gt; Установка и обновление. Затем нажмите на кнопку "Выбрать файл" и после выбора нажмите кнопку "Загрузить".

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/57adaabf90336059d4edf119/file-FjzztGj3fN.png)

4. После этого перейдите в Компоненты-&gt; Joomshopping-&gt; Опции. Далее выберите "Список оплаты" и в появившемся списке найдите unitpay и кликните по ссылке. В открывшемся окне настроек перейдите на вкладку "Конфигурация". В поле DOMAIN вставьте значение unitpay.ru. Также впишите PUBLIC KEY и SECRET KEY, которые вы можете взять в личном кабинете на сайте unitpay.ru. Также здесь вы можете установить статусы, которые будут выдаваться в случае успешной и неудавшейся оплат. Для сохранения изменений нажмите на кнопку "Сохранить".

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5e6765ff2c7d3a7e9ae8ee07/file-AnBcZbLs31.png)

5. Введите в личном кабинете Unitpay.ru обработчик платежей по шаблону [http://&lt;имя](http://xn--%3C-5ddu8i/) вашего сайта&gt;/components/com\_jshopping/payments/pm\_unitpay/callback.php

