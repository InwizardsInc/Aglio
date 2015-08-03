# Get Document from Envelope

This retrieves the specified document from the envelope.
If the account has the Highlight Data Changes feature enabled,
there is an option to request that any changes in the envelope be highlighted.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents/{documentId}
    Optional additions: encrypted={true}, show_changes={true}

## HTTP Method

    GET

## Parameters

The only required parameters are the envelope ID and document ID. The following optional query parameters can be added to the request.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|encrypted|No|Boolean|When true the PDF bytes returned in the response are encrypted for all the key managers configured on your DocuSign account. The documents can be decrypted with the KeyManager Decrypt Document API.|
|show_changes|No|Boolean|Optional. When set to true, any changed fields for the returned PDF are highlighted in yellow and optional signatures or initials outlined in red.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/
                      envelopes/{envelopeId}/documents/{documentId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the PDF document as a byte stream.
If show_changes was included, any changed fields are highlighted in the PDF.
