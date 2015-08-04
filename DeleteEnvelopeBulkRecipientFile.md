# Delete Envelope Bulk Recipient File

This removes the bulk recipient file from an envelope. This cannot be used if the envelope has been sent.

After using this, the bulkRecipientsUri field will not be returned in subsequent GET calls for the envelope, but the recipient will remain as a bulk recipient

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients/{recipientId}/bulk_recipients

## HTTP Method

    DELETE

## Parameters

The only required parameters are the envelope ID and recipient ID.

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}//accounts/{accountId}/envelopes/
    {envelopeId}/recipients/{recipientId}/bulk_recipients
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

    The response returns a success or failure.
