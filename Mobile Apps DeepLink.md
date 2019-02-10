# Mobile Apps DeepLink

Use HalalaH's DeepLink to call HalalaH App with a bill with the amount that is not editable by the payee, once the order is paid the app will recall your app  based on the Callback URL you provide along with the other parameters.

To check your bill payment status, use the web service [HalalaH EMV Code Bill Status V2](HalalaH%20EMV%20Code%20Bill%20Status%20V2.md) 


## HalalaH App URL  `HalalaHeWallet://`

#### Parameters
#### EMV Code Parameters 
- ###### Terminal Unique ID
> terminal=HG00001 `Terminal Label provided by HalalaH`

- ###### Amount
> amount=10.50 `Amount in decimal format`

- ###### Reference Unique ID
> referenceNo=Unique_Order_ID `Unique number to identify order per terminal in HalalaH Platform. Minimum of 12 characters`

- ###### Bill Number
> billNo=1233111 `Bill Number or Invoice number from merchant platform`

- ###### Memo (comments)
> memo=String `Memo or comments "editable by the payee"`

- ###### CallBack Url
> callback=String `Deep link of the merchant app for call back, called on success transaction`

<br />

#### Example
#### Slack calling HalalaH
```
HalalaHeWallet://Transaction?terminal=HG00001&amount=0.02&referenceNo=london50&bil lNo=london123&memo=memo&callback=slack://open
```
