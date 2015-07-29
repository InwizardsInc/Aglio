# Get a List of Biiling Invoices

This returns a list of invoices for the account.
This call can only be used by users with account administrator privileges.
If the from date or to date queries are not used, the response returns invoices for the last 365 days.

## URL

    /accounts/{accountId}/billing_invoices
    Optional query parameters: from_date={dateTime}, to_date={dateTime}

## HTTP Method

    GET

## Parameters

No parameters are required, but the following optional query parameters can be added.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|from_date|No|dateTime|The date/time setting that specifies the date/time when the request begins checking for invoices for the account.|
|to_date|No|dateTime|The date/time setting that specifies the date/time when the request stops checking for invoices for the account.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/billing_invoices
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of invoices for the query timeframe. If the from date or to date queries are not used, the response returns invoices for the last 365 days.

The following example shows the response json body.

### Example Response Body

    {
      "billingInvoices": [
       {
          "amount": "string",
          "taxableAmount": "string",
          "nonTaxableAmount": "string",
          "balance": "string",
          "dueDate": "string",
          "invoiceId": "string",
          "invoiceNumber": "string",
          "pdfAvailable": "string",
          "invoiceUri": "string",
          "invoiceItems": [
            {
              "chargeAmount": "string",
              "chargeName": "string",
              "invoiceItemId": "string",
              "quantity": "string",
              "unitPrice": "string"
            },
            {
              "chargeAmount": "string",
              "chargeName": "string",
              "invoiceItemId": "string",
              "quantity": "string",
              "unitPrice": "string"
            }
          ]
       },
        {
          "amount": "string",
          "taxableAmount": "string",
          "nonTaxableAmount": "string",
          "balance": "string",
          "dueDate": "string",
          "invoiceId": "string",
          "invoiceNumber": "string",
          "pdfAvailable": "string",
          "invoiceUri": "string",
          "invoiceItems": [
            {
              "chargeAmount": "string",
              "chargeName": "string",
              "invoiceItemId": "string",
              "quantity": "string",
              "unitPrice": "string"
            },
            {
              "chargeAmount": "string",
              "chargeName": "string",
              "invoiceItemId": "string",
              "quantity": "string",
              "unitPrice": "string"
            }
          ]
        }
      ],
      "nextUri": "string",
      "previousUri": "string"
    }
