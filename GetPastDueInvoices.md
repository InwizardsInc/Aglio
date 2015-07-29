# Get Past Due Invoices

This returns any past due invoices for the account and notes if payment can be made through the REST API.
This call can only be used by users with account administrator privileges.

## URL

    /accounts/{accountId}/billing_invoices_past_due

## HTTP Method

    GET

## Parameters

There are no required parameters.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/billing_invoices_past_due
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

### Example Response Body

    {
      "pastDueBalance": "string",
      "paymentAllowed": "string",
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
      ]
    }
