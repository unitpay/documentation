# OpenCart



We recommend using the latest version of the platform. If your version is out of date, then it can be updated. More details [here](http://docs.opencart.com/en-gb/upgrading/).

**Project Settings**

1. In your personal account \([https://unitpay.money/partner](https://unitpay.money/partner)\), select Projects in the upper main menu and click Add project. Follow all the steps to create a new project.
2. On the new project page, fill in the **Payment handler** field and enter the following value:

[http://your\_site/index.php?route=extension/payment/unitpay/callback](http://your_site/index.php?route=extension/payment/unitpay/callback) \(where "your\_site" is the site address of your online store\)

![](../../.gitbook/assets/image%20%2857%29.png)

OpenCart 2.0.x-2.2.x requires a **different URL** for the payment processor:

[http://your\_site/index.php?route=payment/unitpay/callback/](http://your_site/index.php?route=payment/unitpay/callback/) \(where "your\_site" is the site address of your online store\)

1. If you want to redirect to a specific page after a successful or unsuccessful payment, then check the Redirect box and enter the addresses of your pages. 

Module Installation:

1. download the module \(latest version is [here](https://github.com/unitpay/opencart2.x-module)\)
2. Unpack the archive.
3. Take the admin and catalog folder and place it in the site\_root\_directory via FTP or SSH. 
4. Log in using administrator account.
5. Go to the Extensions/Payment section.
6. In the list next to Unitpay, click \[Install\].

**Module Setup**

1. Make sure that you have logged in to the site as an admin user.
   1. Go to the Extensions/Payment section.
2. Find Unitpay in the list of payment systems, click \[Edit\] and enter the Domain \(unitpay.money\), Public key \(numeric code of XXX-XXX type available on the Payment Form page\) and Secret key. Enable the module.
3. Save the settings by clicking the \[Save\] button.

