# Void Envelope

This voids a single in-process envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}
    Add {“status”:”voided”, “voidedReason”:”void reason”} to the request body to void the envelope.

## HTTP Method

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
    
    {
      "status":"voided",
      "voidedReason":"voided for incorrect recipient"
    }

## Response

    The response returns success or failure of the operation.
