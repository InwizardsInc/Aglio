# Get Billing Payment Information

This returns information about one or more payments.
If the from date or to date queries or payment ID are not used,
the response returns payment information for the last 365 days.
This call can only be used by users with account administrator privileges.

## URL

    /accounts/{accountId}/billing_payments
    Optional query parameters: from_date={dateTime}, to_date={dateTime}
    
    OR
    
    /accounts/{accountId}/billing_payments/{paymentId}

## HTTP Method

    GET

## Parameters

No parameters are required, but the payment ID can be added to the URL to get information about a single payment and the following optional query parameters can be added.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|from_date|No|datetime|The date/time setting that specifies the date/time when the request begins checking for payments made for the account.|
|to_date|No|datetime|The date/time setting that specifies the date/time when the request stops checking for payments made for the account.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/billing_payments
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
   
   Accept: application/json
   Content-Type: application/json

## Response

The response returns information for a single payment, if a payment ID was used in the URL,
or a list of payments. If the from date or to date queries or payment ID are not used,
the response returns payment information for the last 365 days. If the request was for a single payment ID,
the nextUri and previousUri elements are not returned.

The following example shows the response json body.

### Example Response Body

    {
      "billingPayments": [
       {
        "paymentId": "string",
        "amount": "string",
        "paymentDate": "string",
        "paymentNumber": "string",
        "description": "string"
       },
       {
        "paymentId": "string",
        "amount": "string",
        "paymentDate": "string",
        "paymentNumber": "string",
        "description": "string"
       }
      ],
      "nextUri": "string",
      "previousUri": "string"
    }
