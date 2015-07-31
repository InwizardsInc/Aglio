# Get Envelope Audit Events

This returns the events for this envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/audit_events

## HTTP Method

    GET

## Parameters

The only required parameter is the envelope ID.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}
    /envelopes/{envelopeId}/audit_events
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of audit events, in name/value pairs,
for the specified envelope. The audit events are listed below.

|Name|Value|
|----|-----|
|logTime|The date-time the audit event occurred.|
|Source|The source of the envelope. Values can be web or API.|
|UserName|The name of the user that sent the envelope.|
|Action|The current action status.|
|Message|The message associated with the Action.|
|EnvelopeStatus|Status of the envelope. Values can be Voided, Created, Deleted, Sent, Delivered, Signed, Completed, Declined and TimedOut.|
|ClientIpAddress|The client IP address associated with the action.|
|Information|Base information associated with the action.|
|GeoLocation|The geographic location associated with the action.|
|Language|The language used in the envelope.|

The following example shows the response json body.

### Example Response Body

    {
      "auditEvents":[{
        "eventFields":[{
          "name":"String content",
          "value":"String content"
        }]
      }]
    }
