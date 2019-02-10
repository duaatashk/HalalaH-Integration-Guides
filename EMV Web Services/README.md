# EMV Web Services

Web services allows you to convert data to EMV QR Code, and revert EMV QR Code to Data   


## Prerequisites

Add Classes and php_api folders to a server that is able to run php



## Convert - Web Service 

Convert Data to EMV QR Code 

#### URL
```
base_Url/php_api/convert.php
```
#### Method
```
POST
```
#### Request body type
```
{
 "Content-Type": "application/json"
}
```
#### Request body 
```
{
 "merchant_category_code": 5812,
 "merchant_name": "Halalah Grocery",
 "merchant_city": "Riyadh",
 "postal_code": "12345",
 "merchant_name_ar": "هللة",
 "merchant_city_ar": "الرياض",
 "amount": ".50",
 "bill": "1233111",
 "reference": "Unique_Order_ID",
 "terminal": "HG00001"
}
```
#### Response body 
```
{
 "qr": "00020101021233140010sa.halalah520458125802SA5915Halalah Grocery6006Riyadh61051234564240002AR0104هللة0206الرياض5403.5053036826241010712331110515Unique_Order_ID0707HG0000163043160"
}
```


#### Body Parameters
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

<br />


## Revert - Web Service

Convert  EMV QR Code to Data

#### URL
```
base_Url/php_api/revert.php
```
#### Method
```
POST
```
#### Request body type
```
{
"Content-Type": "application/json"
}
```
#### Request body
```
{
"qr": "00020101021233140010sa.halalah520458125802SA5915Halalah Grocery6006Riyadh61051234564240002AR0104هللة0206الرياض5403.5053036826241010712331110515Unique_Order_ID0707HG0000163043160"
}
```
#### Response body 
```
[
{
"id": "00",
"length": "02",
"content": "01",
"sub": []
},
{
"id": "01",
"length": "02",
"content": "12",
"sub": []
},
{
"id": "33",
"length": "14",
"content": "0010sa.halalah",
"sub": [
{
"id": "00",
"length": "10",
"content": "sa.halalah"
}
]
},
{
"id": "52",
"length": "04",
"content": "5812",
"sub": []
},
{
"id": "58",
"length": "02",
"content": "SA",
"sub": []
},
{
"id": "59",
"length": "15",
"content": "Halalah Grocery",
"sub": []
},
{
"id": "60",
"length": "06",
"content": "Riyadh",
"sub": []
},
{
"id": "61",
"length": "05",
"content": "12345",
"sub": [
{
"id": "12",
"length": "34",
"content": "5"
}
]
},
{
"id": "64",
"length": "24",
"content": "0002AR0104هللة0206الرياض",
"sub": [
{
"id": "00",
"length": "02",
"content": "AR"
},
{
"id": "01",
"length": "04",
"content": "هللة"
},
{
"id": "02",
"length": "06",
"content": "الرياض"
}
]
},
{
"id": "54",
"length": "03",
"content": ".50",
"sub": []
},
{
"id": "53",
"length": "03",
"content": "682",
"sub": []
},
{
"id": "62",
"length": "41",
"content": "010712331110515Unique_Order_ID0707HG00001",
"sub": [
{
"id": "01",
"length": "07",
"content": "1233111"
},
{
"id": "05",
"length": "15",
"content": "Unique_Order_ID"
},
{
"id": "07",
"length": "07",
"content": "HG00001"
}
]
},
{
"id": "63",
"length": "04",
"content": "3160",
"sub": []
}
]
```
