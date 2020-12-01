# LogicBoxes

### Инструкция по настройке и установке модуля.

1. Скачайте [архив](https://github.com/unitpay/logicboxes-module) с модулем.  
2. Скопируйте содержимое директории unitpay из архива на какой-либо ваш хостинг.  
3. Перейти в панели LogicBoxes в меню settings-&gt;finance & billing-&gt;payment gateway-&gt;list/add.  
  
4. Нажать на кнопку "Аdd a gateway", в открывшемся окне внизу нажать "Add it now".

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/551a91dbe4b0221aadf24410/images/580a3a8290336070ba247d08/file-UvUDQyRVRR.png)

5. В gateway url ввести  [http://&lt;](http://xn--%26lt%3B-e6dsg7e/)домен привязанный к вашему хостингу&gt;/unitpay/paymentpage.php6

. Остальные поля настроить по вашему усмотрению и нажать "Save settings".

7. Заполнить поля в config.php на вашем хостинге. $domain = 'unitpay.money', $secret\_key и $public\_key вы можете взять в личном кабинете unitpay. $key вы можете увидеть в настройках панели logicboxes, для этого вам нужно будет пройти в меню settings-&gt;finance & billing-&gt;payment gateway-&gt;list/add и напротив платежной системы unitpay, которую вы только что настроили нажмите кнопку "Manage". В одном из полей открывшегося окна вы увидите значение key.

8. В личном кабинете unitpay пропишите адрес обработчика платежей  [http://&lt;](http://xn--%26lt%3B-e6dsg7e/)домен привязанный к вашему хостингу&gt;/unitpay/postpayment.php

