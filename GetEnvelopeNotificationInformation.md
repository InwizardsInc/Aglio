# Get Envelope Notification Information

This returns the reminder and expiration information for the envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/notification

## HTTP Method

    GET

## Parameters

The only required parameter is the envelope ID.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/notification
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the expiration and reminder settings for the envelope.

The following example shows the response json body.

### Example Response Body

    {
      "expirations": {
        "expireAfter": "String content",
        "expireEnabled": "String content",
        "expireWarn": "String content"
      },
      "reminders": {
        "reminderDelay": "String content",
        "reminderEnabled": "String content",
        "reminderFrequency": "String content"
      }
    }
