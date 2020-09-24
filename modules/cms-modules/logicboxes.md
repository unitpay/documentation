# LogicBoxes

### 

**The Module Setup and Installation Instruction**

1. Download the [archive](https://github.com/unitpay/logicboxes-module) with the module.
2. Copy the contents of the unitpay directory from the archive to any of your hostings.
3. In the LogicBoxes panel, go to the Settings-&gt;finance & billing-&gt;payment gateway-&gt;list/add.

![](../../.gitbook/assets/image%20%2828%29.png)

1. Click on Add a gateway, then click Add it now at the bottom of the opened window.
2. In the gateway url, enter [http://&lt;domain](http://<domain) linked to your hosting&gt;/unitpay/paymentpage.php
3. Configure the other fields at your discretion and click Save settings.
4. Fill in the fields in config.php on your hosting. You can get $domain = 'unitpay.money', $secret\_key and $public\_key in your unitpay account. You can find $key in the logicboxes panel settings. To do this, go to settings-&gt;finance & billing-&gt;payment gateway-&gt;list/add and click the Manage button opposite the unitpay payment system that you have just configured. You will see the key value in one of the fields in the opened window.
5. Enter the address of the payment handler in your unitpay account [http://&lt;domain](http://<domain) linked to your hosting&gt;/unitpay/postpayment.php

