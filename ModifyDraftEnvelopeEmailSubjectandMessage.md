# Modify Draft Envelope Email Subject and Message

This allows senders to change the email subject and message for draft envelope.
Changes to the subject or message is not additive, it replaces the current information.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}

## HTTP Method

    PUT

## Parameters
|Name|Required?|Type|Description|
|----|---------|----|-----------|
|emailSubject|Yes*|String|The subject of the email sent to all recipients. This can be a maximum of 100 characters.<br/>* The emailSubject for an envelope cannot be blank.|
|emailBlurb|No|String|Optional element. The email message body text. If specified it is included in email body for all envelope recipients. This can be a maximum of 10000 characters.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "emailSubject":"string",
      "emailBlurb":"string"
    }

## Response

    The response returns success or failure of the operation and, for failures, an associated error message.
