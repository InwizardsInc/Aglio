# Get Envelope Purge Document Status

This retrieves the current purge state for an envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}

## HTTP Method

    GET

## Parameters

No parameters are required.

## Request

## Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns envelope information, including the current purge state for the envelope.

|Name|Type|Description|
|----|----|-----------|
|purgeState|String|Shows the current purge state for the envelope. The possible values are:<br/><ul><li>unpurged: There has been no successful request to purge documents.</li><li>documents_queued: The envelope documents have been added to the purge queue, but have not been purged.</li><li>documents_and_metadata_queued: The envelope documents and metadata have been added to the purge queue, but have not yet been purged.</li><li>documents_purged: The envelope documents have been successfully purged.</li><li>	documents_and_metadata_purged: The envelope documents and metadata have been successfully purged.</li></ul>


The following example shows the response json body.

### Example Response Body

    {
      "transactionId": "string",
      "status": "string",
      "documentsUri": "string",
      "recipientsUri": "string",
      "asynchronous": "string",
      "envelopeUri": "string",
      "emailSubject": "string",
      "emailBlurb": "string",
      "envelopeId": "string",
      "signingLocation": "string",
      "customFieldsUri": "string",
      "authoritativeCopy": "string",
      "notificationUri": "string ",
      "enforceSignerVisibility": "string",
      "enableWetSign": "string",
      "allowMarkup": "string",
      "allowReassign": "string",
      "createdDateTime": "string",
      "lastModifiedDateTime": "string",
      "deliveredDateTime": "string",
      "sentDateTime": "string",
      "completedDateTime": "string",
      "voidedDateTime": "string",
      "voidedReason": "string",
      "deletedDateTime": "string",
      "declinedDateTime": "string",
      "statusChangedDateTime": "string",
      "documentsCombinedUri": "string",
      "certificateUri": "string",
      "templatesUri": "string",
      "messageLock": "string",
      "recipientsLock": "string",
      "useDisclosure": "string",
      "emailSettings": {
        "replyEmailAddressOverride": "string",
        "replyEmailNameOverride": "string",
        "bccEmailAddresses": [
          {
            "bccEmailAddressId": "string",
            "email": "string"
          },
          {
            "bccEmailAddressId": "string",
            "email": "string"
          }
       ]
      },
      "purgeState": "string"
    }
