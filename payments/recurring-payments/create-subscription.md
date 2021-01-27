# Creating a Subscription

The subscription mechanism allows you to automatically debit money from the card without the client's participation.

This method is useful wherever you need to make periodic payments \(debit rent, top up your phone, pay for Internet access, etc.\).

Creating a subscription includes three steps:

1. Activating this feature with your supervising manager
2. Creating a setup fee with transmitting the additional parameter **params\[subscription\]=true**
3. Getting the subscription ID **subscriptionId** at your project's [payment handler](../payment-handler.md).

After successfully creating a subscription, you can debit funds from the client's card \(the subscription must have the active status\) using the standard mechanism of [creating payment](../create-payment.md) via the API and transmitting the subscription ID to the parameter: **params \[subscriptionId\]=XXX**. The amount and frequency of debiting is determined on the partner's side.

{% hint style="warning" %}
Subscriptions do not work simultaneously with [Payments with Pre-authorization](https://help.unitpay.money/v/en/payments/pre-authorization-payments)
{% endhint %}

