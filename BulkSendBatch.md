# Checking the Status of one Bulk Send Batch

This returns status information about a single bulk recipient batch.
A bulk recipient batch is the set of envelopes sent from a single bulk recipient file.

## URL

    /accounts/{accountId}/bulk_envelopes/{batchId}
    
    Optional query strings: include={all, failed, queued, processing, sent}

## HTTP Method

    GET

## Parameters

The only required parameter is the batchId. The following optional query strings can be added to narrow the response results.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|include|No|String|Sets which entries are included in the response. Multiple entries can be included by using commas in the query string (example: ?include=”failed,queued”)<br/><br/>Valid entries are:<ul><li>all - Returns all entries. If present, overrides all other query settings. This is the default if no query string is provided.</li><li>failed - This only returns entries with a failed status.</li><li>queued - This only returns entries with a queued status.</li><li>processing – This only returns entries with a processing status.</li><li>sent – This only returns entries with a sent status.</li></ul>|

## Response

### Example Response Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/bulk_envelopes/{batchId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
   
    Accept: application/json
    Content-Type: application/json

## Response

The response returns status information about a single bulk recipient batch.

The following example shows the response json body.

### Example Response Body

    {
      "bulkEnvelopeStatuses": [
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
      ],
      "resultSetSize": "string",
      "startPosition": "string",
      "endPosition": "string",
      "totalSetSize": "string",
      "nextUri": "string",
      "previousUri": "string"
    }
