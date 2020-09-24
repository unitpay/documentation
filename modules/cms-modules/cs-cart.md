# CS-Cart

### Инструкция по настройке и установке модуля. <a id="instrukciya-po-nastroike-i-ustanovke-modulya"></a>

1. Скачайте [архив](https://github.com/unitpay/cscart-module/releases/download/1.0.2/cscart-module-1.0.2.zip) с модулем.

2. Выполните запросы из файла install.sql в вашей базе данных.

3. Скопируйте содержимое директории unitpay из архива в корень вашего сайта.

4. В админпанели сайта выберите в меню "Администрирование/способы оплаты".

5. Нажмите + для того, чтобы добавить новый способ оплаты.

6. В появившемся окне:

* введите название для нового способа оплаты,
* выберите в выпадающем списке процессор unitpay,
* выберите категорию оплаты - интернет платежи.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5800c14cc697915a23d793d4/file-f4a2Rtg53K.png)

7. Перейдите во вкладку "Настройки" и введите домен \(unitpay.ru\), публичный и секретный ключи. Эти ключи вы можете взять в личном кабинете unitpay.![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5e69080d2c7d3a7e9ae905c3/file-NuCjKo9cBV.png)

8. Нажмите "Создать" для того, чтобы создать новый способ оплаты.

9. В личном кабинете unitpay введите путь к обработчику платежей по шаблону: [http://&lt;адрес](http://xn--/%3C-8cdug0fj/) вашего сайта&gt;/unitpay/callback.php![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5800c3a9c697915a23d793e9/file-6rY1j5zahv.png)

