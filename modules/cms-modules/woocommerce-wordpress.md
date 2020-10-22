# Woocommerce Wordpress

### Инструкция по настройке и установке модуля. <a id="instrukciya-po-nastroike-i-ustanovke-modulya"></a>

**Важно!!!** Если вы используете Wordpress и для формирования запросов к нашей платформе пользуетесь не нашим модулем, а [api](https://help.unitpay.ru/payments/create-payment), то вам необходимо обратиться к менеджеру UnitPay для помещения вашего IP в белый список.

1. Скачайте [архив](https://github.com/unitpay/woocommerce-module/archive/2.1.1.zip) с модулем.

2. Скопируйте содержимое директории unitpay в архиве в директорию /&lt;корень сайта&gt;/wp-content/plugins/.

3. Зайдите в "Плагины"-&gt; "Установленные" и нажмите "Активировать" напротив плагина UnitPay.

4. Выберите в меню "WooCommerce" -&gt; "Настройки" и перейдите на вкладку "Платежи", там выберите UnitPay.

5. В поле DOMAIN вставьте значение unitpay.money. В поля PUBLIC KEY и SECRET KEY скопируйте публичный и секретный ключ, которые вы можете взять из личного кабинета Unitpay. Нажмите на кнопку "Сохранить изменения".  
  
.![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5e68dc452c7d3a7e9ae90273/file-mPvwuDGXSV.png)

6. Введите в личном кабинете Unitpay обработчик платежей по шаблону [http://&lt;имя\_вашего\_сайта&gt;](http://xn--/%3C__-7vebaolv6au8a9a1ct4h3f/)/?wc-api=wc\_unitpay![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/579634b7c6979160ca147078/file-YJh47Ao3iN.png)

