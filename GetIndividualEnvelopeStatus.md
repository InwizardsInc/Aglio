# Get Individual Envelope Status

This returns the overall status for a single envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}

## HTTP Method

    GET

## Parameters

The only required parameter is the envelope ID.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>
                               {integrator_key}</IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the current envelope status.

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
      "notification": {
        "useAccountDefaults": "string",
        "reminders": {
          "reminderEnabled": "string",
          "reminderDelay": "string",
          "reminderFrequency": "string"
        },
      "expirations": {
        "expireEnabled": "string",
        "expireAfter": "string",
        "expireWarn": "string"
      }
      },
      "notificationUri": "string",
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
      "messageLock": "string1",
      "recipientsLock": "string",
      "useDisclosure": "string",
      "emailSettings": {
        "replyEmailAddressOverride": "string",
        "replyEmailNameOverride": "string",
        "bccEmailAddresses": [
         {
            "bccEmailAddressId": "string",
            "email": "string"
         }
       ]
      },
      "purgeState": "string",
      "lockInformation": {
       "lockedByUser": {
          "userName": "string",
          "email": "string",
          "userId": "string",
          "userType": "string",
          "userStatus": "string",
          "uri": "string",
        }
      }
    }
    }
