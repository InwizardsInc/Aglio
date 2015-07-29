# Get a Billing Invoice

This returns the requested invoice. This call can only be used by users with account administrator privileges.

## URL

    /accounts/{accountId}/billing_invoices/{invoiceId}

## HTTP Method

    GET

## Parameters

No parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/billing_invoices/{invoiceId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the requested invoice information.

>**Note:**  If pdfAvailable in the response is true, a PDF version of this invoice can be downloaded.
>To get the PDF, make the call again and change “Accept:” in the header to “Accept: application/pdf”

The following example shows the response json body.

### Example Response Body

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

