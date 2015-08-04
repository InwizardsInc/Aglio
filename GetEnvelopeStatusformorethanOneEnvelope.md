# Get Envelope Status for more than One Envelope

This returns envelope status for the requested envelopes.

## URL

    /accounts/{accountId}/envelopes/status

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|envelopeIds|Yes|String|The envelope IDs for the envelopes being requested.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/status?envelope_ids=request_body
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "envelopeIds":[
        "String content",
        "String content"
      ],
    }

## Response

The response returns the envelope status information for the requested envelopes.

The following example shows the response json body.

### Example Response Body

    {
      "envelopes": [{
        "certificateUri": "String content",
        "customFieldsUri": "String content",
        "documentsCombinedUri": "String content",
        "documentsUri": "String content",
        "envelopeId": "String content",
        "envelopeUri": "String content",
        "notificationUri": "String content",
        "recipientsUri": "String content",
        "status": "String content",
       "statusChangedDateTime": "String content"
      },
      {
        "certificateUri": "String content",
        "customFieldsUri": "String content",
        "documentsCombinedUri": "String content",
        "documentsUri": "String content",
        "envelopeId": "String content",
        "envelopeUri": "String content",
        "notificationUri": "String content",
        "recipientsUri": "String content",
        "status": "String content",
        "statusChangedDateTime": "String content"
      },}],
      }],
      "resultSetSize": "String content"
    }
