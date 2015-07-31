# Get Envelope Custom Field Information

This returns the custom field information for a single envelope.
These fields can be used in the envelopes for your account to record
information about the envelope, help search for envelopes and track information.
The envelope custom fields are shown in the Envelope Settings section when a user
is creating an envelope in the DocuSign member console. The envelope custom fields are
not seen by the envelope recipients.

There are two types of envelope custom fields, text and list. A text custom field
lets the sender enter the value for the field. With a list custom field, the sender
selects the value of the field from a pre-made list.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/custom_fields

## HTTP Method

    GET

## Parameters

The only required parameter is the envelope ID.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}
    /envelopes/{envelopeId}/custom_fields
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns information about the custom fields included in the envelope.
The response splits the custom fields by list and text types. If there are no custom
fields in the envelope, the response returns an empty list.

|Name|Type|Description|
|----|----|-----------|
|listCustomFields||
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;fieldId|String|The DocuSign generated ID number for the Envelope Custom Field.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;name|String|The name of the Envelope Custom Field|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;required|String|When true, information must be entered into the custom field to send the envelope.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;show|String|When true, the custom field is shown to senders in the DocuSign member console during sending.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;value|String|The selected value for the field.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;listItems|String|The list of values that can be selected by senders. The list values are separated by semicolons. Example: [one,two;three;four"]|
|textCustomFields||
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;fieldId|String|The DocuSign generated ID number for the Envelope Custom Field.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;name|String|The name of the Envelope Custom Field|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;required|String|When true, information must be entered into the custom field to send the envelope.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;show|String|When true, the custom field is shown to senders in the DocuSign member console during sending.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;value|String|The entered value for the field.|

The following example shows the response json body.

### Example Response Body

    {
      "listCustomFields":[{
        "fieldId": "String content",
        "name": "String content",
        "required": "String content",
        "show": "String content",
        "value":"String content",
        "listItems":["String content"]
      }]
      "textCustomFields":[{
        "fieldId": "String content",
        "name": "String content",
        "required": "String content",
        "show": "String content",
        "value":"String content"
      }]
    }
