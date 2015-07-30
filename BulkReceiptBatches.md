# Check Status of all Bulk Recipient Batches

This returns status information about all the bulk recipient batches.
A bulk recipient batch is the set of envelopes sent from a single bulk recipient file.
The response includes general information about each bulk recipient batch.

## URL

    /accounts/{accountId}/bulk_envelopes
    
    Optional query strings: count={integer 1 to 20}, start_position={integer}

## HTTP Method

    GET

## Parameters

No additional parameters are required, but the following optional query strings can be added to narrow the response results.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|count|No|Integer|The number of results to return. This can be 1 to 20.|
|start_position|No|Integer|The position of the bulk envelope items in the response. This is used for repeated calls, when the number of bulk envelopes returned is too large for one return. The default value is 0.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/bulk_envelopes
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
   
    Accept: application/json
    Content-Type: application/json

## Response

The response returns information about the envelopes sent with bulk recipient batches,
including the batchId, which can be used to retrieve a more detailed status of individual bulk recipient batches.

The following example shows the response json body.

### Example Request Body

    {
      "batchSize": "string",
      "batchId": "string",
      "bulkEnvelopesBatchUri": "string",
      "failed": "string",
      "queued": "string",
      "sent": "string",
      "submittedDate": "string",
      "resultSetSize": "string",
      "startPosition": "string",
      "endPosition": "string",
      "totalSetSize": "string",
      "nextUri": "string",
      "previousUri": "string",
      "bulkEnvelopes": [
       {
          "transactionId": "string",
          "submittedDateTime": "string",
          "envelopeId": "string",
          "envelopeUri": "string",
          "bulkRecipientRow": "string",
          "name": "string",
          "email": "string",
          "bulkStatus": "string"
        }
      ]
    }
