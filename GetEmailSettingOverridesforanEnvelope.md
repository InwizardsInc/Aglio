# Get Email Setting Overrides for an Envelope

This retrieves email override settings for the envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/email_settings

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/email_settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the email setting information for the envelope,
including the bccEmailAddressId associated with the bccEmailAddresses.

The following example shows the response json body.

### Example Response Body

    {
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
    }
