# Drupal 7 \(commerce\)

**The Module Setup and Installation Instruction**

1. Download the [archive](https://github.com/unitpay/commerce-module/archive/master.zip) with the module.
2. Install the module. To do this, copy the contents of the Unitpay directory from the archive to the address &lt;folder with your site&gt;/sites/all/modules. After that, click Modules in the menu, check the box next to Unitpay and click Save сonfiguration.

![](../../.gitbook/assets/image%20%2826%29.png)

3. Then go to Store -&gt; Configure store -&gt; Payment methods -&gt; edit Unitpay and click the Edit button opposite the Enable payment method: Unitpay. In the DOMAIN field, insert the value of unitpay.money and copy the public and secret key from the Unitpay account in the PUBLIC KEY and SECRET KEY fields.

![](../../.gitbook/assets/image%20%2815%29.png)

4. Enter the payment handler in your Unitpay.ru account using the template: [http://&lt;your\_site\_name&gt;/unitpay/callback&gt;/unitpay/callback](http://<your_site_name>/unitpay/callback>/unitpay/callback)

