# Magento 2

### Instructions for configuring and installing the module. <a id="instrukciya-po-nastroike-i-ustanovke-modulya"></a>

1.Download the [module archive](https://github.com/unitpay/magento2/archive/main.zip) and upload it to the site root.  


2. In the shell from the site root to run the command php bin/magento setup:upgrade to install module  


3. php bin/magento setup:di:compile for compiling configuration files  


4. Go to the admin panel. Stores -&gt; Configuration

![](../../.gitbook/assets/image2%20%281%29.png)

5. In the left menu, select Sales -&gt; Payment Methods

![](../../.gitbook/assets/image7%20%281%29.png)

6. Find the unitpay module and set the settings Domain \(**unitpay.ru**\), Public Key, Secret Key \(you can take it in the project settings in your personal account Unitpay\)

![](../../.gitbook/assets/image6.png)

7. By default, delivery is valid for each product \(3 products = triple the cost of delivery\). To configure this, go to Stores -&gt; Configuration.Then in the sales drop down list Sales we look for Shipping methods

![](../../.gitbook/assets/image4%20%281%29.png)

