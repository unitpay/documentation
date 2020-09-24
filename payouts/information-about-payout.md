# Information about Payout

To get it from the API, use the [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk) library.![](https://gblobscdn.gitbook.com/assets%2F-M9Y_k8Gr-WxeECFRelw%2F-MA1PsbiuaLGnU-0ocfd%2F-MA1RaPirDY4oXdtF6Pt%2Fimage.png?alt=media&token=f6855aa7-7358-4663-9381-4e8f491cf1a7)

| ​ | **Value** | **Description** |
| :--- | :--- | :--- |
| **login** | line | Partner's email in the UnitPay system |
| **secretKey** | line | Partner's secret key, available in the [profile settings](https://unitpay.money/partner/profile/edit)​ |
| **transactionId** | text | Unique payout ID on the partner's side |

You can run the query in test mode. [Learn more](https://help.unitpay.ru/v/master/book-of-reference/test-api)​

**Successful response**![](https://gblobscdn.gitbook.com/assets%2F-M9Y_k8Gr-WxeECFRelw%2F-MA1PsbiuaLGnU-0ocfd%2F-MA1RgtK4-iE7jl_7rqt%2Fimage.png?alt=media&token=c5e10bcb-a39e-4bfa-b42d-dbc7d40c4bd6)

| ​ | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | The comment of a successful operation can be used as a hint to the user after completing the request |
| **status** | line | success — successful payout not\_completed — the payout has been sent to the payment system but no confirmation has been received yet \(temporary status\) |
| **payoutId** | number | Unique payout ID in the UnitPay system |
| **partnerBalance** | number | Partner's balance in the system available for payments |
| **createDate** | text | Payout creation date |
| **completeDate** | text | Payout completion date |
| **sum** | number | Amount of payout |
| **payoutCommission** | number | Payout commission |
| **partnerCommission** | number | Partner commission |

**Error response**![](https://gblobscdn.gitbook.com/assets%2F-M9Y_k8Gr-WxeECFRelw%2F-MA1PsbiuaLGnU-0ocfd%2F-MA1RmvXybvn1ak5EB7_%2Fimage.png?alt=media&token=a32412cc-2b6f-4f6a-8152-f728543d268f)

| ​ | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | Information with a description of the request error |
| **code** | line | Error code, see detailed explanation in the table below |

**Errors:**

| ​ | **Description** |
| :--- | :--- |
| **100** | Mass payment service is disabled |
| **101** | Mass payment service is not available for you |
| **102** | The minimum amount of a single payment should be more than 1 ruble |
| **103** | The payout amount should be less than or equal to the current balance |
| **104** | The phone number is not included in the list of countries available for payouts |
| **105** | We could not get information about the payee's purse. Check the purse number and try to repeat the transaction again or after a while |
| **106** | The maximum amount of a single payment should not exceed 15,000 rubles |
| **201** | We could not transfer funds to the account you specified. This may be due to the restrictions on the payee's account or errors on the payment system platform. Please contact our customer support for more information or repeat the request later |

**Technical error:**

| ​ | **Description** |
| :--- | :--- |
| **-32000** | Authorization error |
| **-32602** | Invalid request parameters |
| **-32603** | Internal technical error |

