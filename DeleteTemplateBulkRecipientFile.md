# Delete Template Bulk Recipient File

This removes the bulk recipient file from a template.

After using this, the bulkRecipientsUri field will not be returned in
subsequent GET calls for the template, but the recipient will remain as a bulk recipient.

## URL

    /accounts/{accountId}/templatess/{templateId}/recipients/{recipientId}/bulk_recipients

## HTTP Method

    DELETE

## Parameters

The only required parameters are the template ID and recipient ID.

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}//accounts/{accountId}/
    templates/{templateId}/recipients/{recipientId}/bulk_recipients
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

    The response returns a success or failure.
