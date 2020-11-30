# Drupal 7 \(commerce\)

### Инструкция по настройке и установке модуля. <a id="instrukciya-po-nastroike-i-ustanovke-modulya"></a>

1. Скачайте [архив](https://github.com/unitpay/commerce-module) с модулем.

2. Установите модуль. Для этого скопируйте содержимое директории unitpay из архива по адресу &lt;папка с вашим сайтом&gt;/sites/all/modules. После этого нажмите в меню "Модули", поставьте галочку напротив Unitpay и нажмите на кнопку "Save configuration".  
  
![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5790e6dac6979160ca145f87/file-sI2HHz5cfy.png)

3. Затем пройдите к Store -&gt; Configure store -&gt; Payment methods -&gt; edit Unitpay и нажмите на кнопочку "Edit" напротив пункта "Enable payment method: Unitpay". В поле DOMAIN вставьте значение unitpay.money, в поля PUBLIC KEY и SECRET KEY скопируйте публичный и секретный ключ из личного кабинета Unitpay.  
  
![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5e68c38e2c7d3a7e9ae90120/file-ZT3pa1HeMz.png)

4. Введите в личном кабинете Unitpay.ru обработчик платежей по шаблону [http://&lt;имя\_вашего\_сайта&gt;/unitpay/callback](http://xn--/%3C__-7vebaolv6au8a9a1ct4h3f/)&gt;/unitpay/callback![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5790eaed9033602936037f10/file-d5eQvOskcg.png)

