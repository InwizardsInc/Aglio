# Republish Connect Information for One Envelope

This is used to republish Connect information for a single envelope.

## URL

    /accounts/{accountId}/connect/envelopes/{envelopeId}/retry_queue

## HTTP Method

    PUT

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect/envelopes/{envelopeId}
                            /retry_queue
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>{password}
                              </Password><IntegratorKey>{integrator_key}</IntegratorKey>
                              </DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a success or failure and the information about the retry queue for the request.

The following example shows the response json body.

### Example Response Body

    {
      "retryQueue":[{
        "configId":"String content",
        "configUrl":"String content",
        "envelopeId":"String content",
        "status":"String content",
        "statusMessage":"String content"
      }]
    }
