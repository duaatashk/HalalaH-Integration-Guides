# PHP EMV Code Generation
PHP piece allows you to generate EMV Code using the required parameters


## Prerequisites

Add Classes folder to a server that is able to run php

## Convert
use the `$inputs` array in `Qrcode` function to get `$Qrcode` Object
```
$Qrcode = new Qrcode($inputs);
echo $Qrcode->output();
```

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


#### Example

```
require_once './classes/Qrcode.php';

$inputs = array(
    "merchant_category_code"=> 5812,
    "merchant_name"=> "Halalah Grocery",
    "merchant_city"=> "Riyadh",
    "postal_code"=> "12345",
    "merchant_name_ar"=> "هللة",
    "merchant_city_ar"=> "الرياض",
    "amount"=> ".50",
    "bill"=> 1233111,
    "reference"=> "Unique_Order_ID",
    "terminal"=> "HG00001"
);

$Qrcode = new Qrcode($inputs);
echo $Qrcode->output();
```

#### Output

```
00020101021233140010sa.halalah520458125802SA5915Halalah Grocery6006Riyadh61051234564240002AR0104هللة0206الرياض5403.5053036826241010712331110515Unique_Order_ID0707HG0000163043160
```
