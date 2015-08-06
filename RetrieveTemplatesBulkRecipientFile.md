# Retrieve Templates Bulk Recipient File

This is used to retrieve the bulk recipient file information for a template with a bulk recipient.

## URL

    /accounts/{accountId}/templatess/{templateId}/recipients/{recipientId}/bulk_recipients

## HTTP Method

    GET

## Parameters

The only required parameters are the template ID and recipient ID.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}//accounts/{accountId}/templates/
    {templateId}/recipients/{recipientId}/bulk_recipients
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the recipient information for each row of the bulk recipient csv file,
the total number of recipients in the file, and the bulkRecipientUri.

The following example shows the response json body.

### Example Response Body

    {
      "bulkRecipients": [
        {
          "rowNumber": "string",
          "email": "string",
          "name": "string",
          "note": "string",
          "accessCode": "string",
          "identification": "string",
          "phoneNumber": "string",
          "tabLabels": [
            {
              "name": "string,"
              "value": "string"
            }
          ]
        },
        {
          "rowNumber": "string",
          "email": "string",
          "name": "string",
          "note": "string",
          "accessCode": "string",
          "identification": "string",
          "phoneNumber": "string",
          "tabLabels": [
            {
              "name": "string,"
              "value": "string"
            }
          ]
        }
      ],
      "bulkRecipientsCount": "string",
      "bulkRecipientsUri": "string"
    }
