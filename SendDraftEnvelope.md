# Send Draft Envelope

This sends a single draft envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}
    Add {“status”:”sent”} to the request body to send the envelope.

## Http Method

    PUT

## Parameters

    The only required parameter is the envelope ID.

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {"status":"sent"}
    

## Response

    The response returns success or failure of the operation.
