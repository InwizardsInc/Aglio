# Purchase Additional Envelopes

>**IMPORTANT:**  At this time, this operation is limited to DocuSign internal use only.

This completes the purchase of envelopes for your account.
The actual purchase is done as part of an internal workflow interaction with an envelope vendor.

## URL

    /accounts/{accountId}/billing_plan/purchased_envelopes

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|amount|Yes|String|The total amount of the purchase.|
|appName|No|String|The AppName of the client application.|
|currencyCode|No|String|The CurrencyCode of the purchase. This is based on the ISO 4217 currency code information.|
|platform|No|String|The Platform of the client application|
|productId|No|String|The Product ID from the AppStore.|
|quantity|Yes|String|The quantity of envelopes to add to the account.|
|receiptData|No|String|The encrypted Base64 encoded receipt data.|
|storeName|No|String|The name of the AppStore.|
|transactionId|No|String|The Transaction ID from the AppStore.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/billing_plan/Purchased_envelopes
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                                {password}</Password><IntegratorKey>{integrator_key}
                                </IntegratorKey></DocuSignCredentials>
    
    {
      "amount":"String content",
      "appName":"String content",
      "currencyCode":"String content",
      "platform":"String content",
      "productId":"String content",
      "quantity":"String content",
      "receiptData":"String content",
      "storeName":"String content",
      "transactionId":"String content"
    }
