# Card Information by BIN

To get it from the API, we recommend using the [Unitpay PHP-SDK](https://github.com/unitpay/php-sdk) library.![](https://gblobscdn.gitbook.com/assets%2F-M9Y_k8Gr-WxeECFRelw%2F-MA1PsbiuaLGnU-0ocfd%2F-MA1SJgP12meqOSDd7ci%2Fimage.png?alt=media&token=34130cce-ac4e-4ae2-94f4-d72a5bb980d5)

| ​ | **Value** | **Description** |
| :--- | :--- | :--- |
| **login** | line | Partner's email in the UnitPay system |
| **secretKey** | line | Partner's secret key, available in the [profile settings](https://unitpay.money/partner/profile/edit)​ |
| **bin** | number | First 6 digits of the card number |

**Successful response**![](https://gblobscdn.gitbook.com/assets%2F-M9Y_k8Gr-WxeECFRelw%2F-MA1PsbiuaLGnU-0ocfd%2F-MA1SOp9TY4nkRqBRc42%2Fimage.png?alt=media&token=392aac82-46bd-464b-a2d8-831a4814e6e4)

| ​ | **Value** | **Description** |
| :--- | :--- | :--- |
| **bin** | line | First 6 digits of the card number |
| **bank** | line | Name of the bank where the card was issued |
| **countryCode** | line | Country code in Alpha-2 format \(ISO 3166-1\) |
| **brand** | line | Name of the international system which the card is served in. |
| **category** | line | Card category |
| **type** | line | Card type |
| **bankUrl** | line | Bank Url |
| **bankPhone** | line | Bank phone number |

**Error response**![](https://gblobscdn.gitbook.com/assets%2F-M9Y_k8Gr-WxeECFRelw%2F-MA1PsbiuaLGnU-0ocfd%2F-MA1SUgIQuwxdUgyPl-y%2Fimage.png?alt=media&token=66ee4127-0324-423c-9288-5a80cfee868e)

| ​ | **Value** | **Description** |
| :--- | :--- | :--- |
| **message** | line | Information with a description of the request error |
| **code** | line | Error code, see detailed explanation in the table below |

**Errors:**

| ​ | **Description** |
| :--- | :--- |
| **100** | No matches were found for your query |

**Technical errors:**

| ​ | **Description** |
| :--- | :--- |
| **-32000** | Authorization error |
| **-32602** | Invalid request parameters |
| **-32603** | Internal technical error |

