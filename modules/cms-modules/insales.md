# InSales

**Instruction on Integration of Payment via Unitpay System**

1. Go to the Settings page in the InSales admin panel.
2. Select Payment from the menu.
3. On the Payment Method page, create a new payment method by selecting External Payment Method in the drop-down list and clicking Add.
4. In the Store ID field, enter the PUBLIC KEY of your project in Unitpay.
5. In the Password field, enter the SECRET KEY of your project in Unitpay.
6. In the URL field of the external service, enter [https://unitpay.money/insales](https://unitpay.money/insales).
7. Important Note! Leave the Send detailed order information field empty.
8. Save the page.
9. Go to the project management panel in Unitpay.
10. In the URL field of the Payment Handler section, enter [https://unitpay.money/insales/handler](https://unitpay.money/insales/handler).
11. Save the project settings.

**Integration is complete.**

{% hint style="warning" %}
Do not use the url from the "URL to go to on successful payment/error" fields inside Insales to redirect users after successful/erroneous payment. These are technical addresses, and there will be a 404 error when clicking on them.
{% endhint %}

**Should you have any questions, please do not hesitate to contact your account manager or use our 24/7 Unit.Help chat widget.**

