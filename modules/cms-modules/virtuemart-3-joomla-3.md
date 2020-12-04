# VirtueMart 3 \(joomla 3\)

**The Module Setup and Installation Instruction**

1. Download the [archive](https://github.com/unitpay/virtuemart-module/archive/master.zip) with the module. The module was tested on VirtueMart 3 with Joomla 3.5.1
2. Go to the site admin panel.
3. Install the module. To do this, go to Extensions-&gt;Extension manager-&gt;Install. Then click on the Select file button and after selecting it, click Upload & Install.

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y4yprez09qYRw6kNE%2F0.png?alt=media)

4. Next, in the top menu, go to VirtueMart -&gt; Payment methods

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y4ypsQ73RWeTw4DBU%2F1.png?alt=media)

5. Click the Create button and enter the required information such as the name of the payment method, etc. Select Unitpay in the payment method list. Then click Save.

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y4yptiTR0En8L7Dpl%2F2.png?alt=media)

6. After that go to the Configuration tab of this module settings and enter the value of unitpay.money in the DOMAIN field. You can find PUBLIC KEY and SECRET KEY fields in your personal account on the Unitpay.money website, then click the Save button.

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y4ypuXvWMltl7eFaH%2F3.png?alt=media)

7. Enter the payment handler in your Unitpay account using the template [http://&lt;your](http://%3Cyour/) site name&gt;/index.php?option=com\_virtuemart&view=pluginresponse&task=pluginnotification&tmpl=component&format=json

![](https://gblobscdn.gitbook.com/assets%2Fdokumentacziya%2F-M9xezG_6tZ_3GRmvyig%2F-M9y4ypvH0BGteYIrwXb%2F4.png?alt=media)

