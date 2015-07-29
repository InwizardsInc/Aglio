# Get All Account Payments

This allows users with account administrator privileges to pay a past due invoice.
This call can only be used by users with account administrator privileges.

>**Note** This can only be used if the paymentAllowed value for a past due invoice is true.
>This can be determined using Get Past Due Invoices.

## URL

    /accounts/{accountId}/billing_payments

## HTTP Method

    POST

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|paymentAmount|Yes|String|The payment amount for the past due invoices. This value must match the pastDueBalance value retrieved using Get Past Due Invoices.|

## Request

### Example Requset Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/billing_payments
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json
    {
      "paymentAmount": "string"
    }

## Response

The response returns invoice and payment information for the past due invoices.

The following example shows the response json body.

### Example Response Body

    {
      "billingPayments": [
       {
          "invoiceId": "string",
          "paymentId": "string",
          "amount": "string"
       },
       {
          "invoiceId": "string",
          "paymentId": "string",
          "amount": "string"
        }
      ]
    }
