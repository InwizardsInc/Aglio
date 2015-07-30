# Republish Connect Information for Multiple Envelopes

This is used to republish Connect information for the set of envelopes.
The primary use is to republish Connect post failures by including envelope IDs
for the envelopes that failed to post in the request. The list of envelope IDs
that failed to post correctly can be retrieved by getting the failure log.

## URL

    /accounts/{accountId}/connect/envelopes/retry_queue

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|envelopeIds|Yes|String|An array list of envelope Id’s to be republished.|
|synchronous|No|Boolean|If true, the system attempts to publish failed posts again and returns the status of the post attempt.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect/envelopes/retry_queue
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>{password}
                               </Password><IntegratorKey>{integrator_key}</IntegratorKey>
                               </DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "envelopeIds":["String content","String content","String content"],
      "synchronous":"String content"
    }

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
