# Remove a Page

This removes a page from a document based on the page ID.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents/{documentId}/pages/{pageId}

## HTTP Method

    DELETE

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/
    envelopes/{envelopeId}/documents/{documentId}/pages/{pageId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

    The response returns a success or failure.
