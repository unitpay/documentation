# VirtueMart 3 \(joomla 3\)

### Инструкция по настройке и установке модуля. <a id="instrukciya-po-nastroike-i-ustanovke-modulya"></a>

1. Скачайте [архив](https://github.com/unitpay/virtuemart-module) с модулем. Модуль тестировался на VirtueMart 3 с Joomla 3.5.1

2. Зайдите в админ-панель сайта.

3. Установите модуль. Для этого перейдите в Расширения-&gt;Менеджер расширений-&gt;Установить. Затем нажмите на кнопку "Выбрать файл", и после выбора нажмите кнопку Upload & Install.  
  
![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/57891cbdc697912dee72b9bd/file-ZnqxZL1aUp.png)

4. Далее, перейдите в верхнем меню в VirtueMart-&gt;Методы оплаты.  
  
![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/57891ce4c697912dee72b9be/file-Ca3lNwEm7r.png)

5. Нажмите на кнопку "Создать" и введите требуемые данные, такие как: имя метода оплаты и т.п. В методе оплаты выберите Unitpay. Затем нажмите кнопку "Сохранить".  
  
![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/57891cf8c697912dee72b9bf/file-8LMiJ7nHUN.png)

6. Затем перейдите на вкладку "Конфигурация" настроек данного модуля и введите в поле DOMAIN значение unitpay.money. Поля PUBLIC KEY и SECRET KEY вы можете взять в личном кабинете на сайте Unitpay.money, затем нажмите на кнопку "Сохранить".  
  
![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/5e674e902c7d3a7e9ae8ed2a/file-OhmvJJMNF3.png)

7. Введите в личном кабинете Unitpay.money обработчик платежей по шаблону [http://&lt;имя](http://xn--/%3C-5ddu8i/) вашего сайта&gt;/index.php?option=com\_virtuemart&view=pluginresponse&task=pluginnotification&tmpl=component&format=json  
  
![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/57891d68c697912dee72b9c2/file-yUsASL61kJ.png)

