# Dot Net EMV Code Generation
A library allows you to generate an EMV Code 


## Prerequisites

1- Create DotNet Project

2- Add EmvQrCode.dll as Reference



#### Parameters
- ###### Merchant Category Code
> "merchant_category_code": 5812 `Four digits ISO Code for Merchant Category Code. Provided by HalalaH` 

- ###### Merchant Name
> "merchant_name": "Halalah Grocery" `Merchant Name in (English) Language`

- ###### Merchant City
> "merchant_city": "Riyadh" `Merchant City in (English) Language`

- ###### Merchant Postal Code
> "postal_code": "12345" `Five digits for Merchant Location Postal Code`

- ###### Merchant Name
> "merchant_name_ar": "هللة" `Merchant Name in (Arabic) Language`

- ###### Merchant City
> "merchant_city_ar": "الرياض" `Merchant City in (Arabic) Language`

- ###### Amount
> "amount": "10.50" `Amount in decimal format`

- ###### Bill Number
> "bill": "1233111" `Bill Number or Invoice number from merchant platform`

- ###### Reference Unique ID
> "reference": "Unique_Order_ID" `Unique number to identify order per terminal in HalalaH Platform. Minimum of 12 characters`

- ###### Terminal Unique ID
> "terminal": "HG00001" `Terminal Label provided by HalalaH`

<br />


## Example 

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.UI;
using System.Web.UI.WebControls;
using EmvQrCode;

namespace TestWebApplication
{
    public partial class WebForm1 : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            Qrcode qr = new Qrcode();

            qr.Merchant_category_code = "5812";
            qr.Merchant_name = "Halalah Grocery";
            qr.Merchant_city = "Riyadh";
            qr.Postal_code = "12345";
            qr.Merchant_name_ar = "هللة";
            qr.Merchant_city_ar = "الرياض";
            qr.Amount = ".50";
            qr.Bill = "1233111";
            qr.Reference = "Unique_Order_ID";
            qr.Terminal = "HG00001";
            
            Response.Write(qr.output());

        }
    }
}
```

###### Output

```
00020101021233140010sa.halalah520458125802SA5915Halalah Grocery6006Riyadh61051234564240002AR0104هللة0206الرياض5403.5053036826241010712331110515Unique_Order_ID0707HG0000163043160
```
