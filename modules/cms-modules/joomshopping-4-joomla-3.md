# Joomshopping 4 \(joomla 3\)

**The Module Setup and Installation Instruction**

1. Download the [archive](https://github.com/unitpay/jshopping-module/releases/download/v2.0.1/jshopping-module-2.0.1.zip) with the module. The module was tested on Joomla 3.9.11 + Joomshopping 4.18.3
2. Go to the site admin panel.
3. Install the module. To do this, go to Components-&gt; Joomshopping-&gt; Install and update. Then click on the Select file button and after selecting it, click the Upload button.

![](../../.gitbook/assets/image%20%2862%29.png)

1. Next go to Components -&gt; Joomshopping -&gt; Options. Then select Payment List, then find Unitpay in the opened list and click on the link. In the opened Settings window, go to the Configuration tab. In the DOMAIN field, insert the value of unitpay.money. In the same field, enter PUBLIC KEY and SECRET KEY which you can find in your unitpay.money account. Here, you can also set the statuses that will be shown in case of successful or failed payment. Click the Save button to save your changes.

![](../../.gitbook/assets/image%20%2859%29.png)

1. Enter the payment handler in your Unitpay.money account using the template: [http://&lt;your](http://<your) site name&gt;/components/com\_jshopping/payments/pm\_unitpay/callback.php

