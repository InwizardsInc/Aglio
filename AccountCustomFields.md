# Get List of Account Custom Fields

This retrieves a list of envelope custom fields associated with the account.
These fields can be used in the envelopes for your account to record information about the envelope,
help search for envelopes and track information. The envelope custom fields are shown in the
Envelope Settings section when a user is creating an envelope in the DocuSign member console.
The envelope custom fields are not seen by the envelope recipients.

There are two types of envelope custom fields, text and list.
A text custom field lets the sender enter the value for the field.
The list custom field lets the sender select the value of the field from a premade list.

## URL

    /accounts/{accountId}/custom_fields

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/custom_fields
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>
                               {integrator_key}</IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of list custom fields and text custom fields associated with the account.

|Name|Type|Description|
|----|----|-----------|
|listCustomFields||
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;name|String|The name of the Envelope Custom Field|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;required|String (Boolean)|When true, information must be entered into the custom field to send the envelope.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;show|String (Boolean)|When true, the custom field is shown to senders in the DocuSign member console during sending.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;listItems|String|The list of values that can be selected by senders. The list values are separated by semi-colons.<br/> Example: [one;two;three;four].|
|textCustomFields||
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;name|String|The name of the Envelope Custom Field|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;required|String (Boolean)|When true, information must be entered into the custom field to send the envelope.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;show|String (Boolean)|When true, the custom field is shown to senders in the DocuSign member console during sending.|

The following example shows the response json body.

## Example Response Body

    {
      "listCustomFields": [{
        "name":"String",
        "required":"String",
        "show":"String",
        "listItems": ["String";"String"]
      },
      {
        "name":"String",
        "required":"String",
        "show":"String",
        "listItems": ["String";"String"]
      }],
      "textCustomFields": [{
        "name":"String",
        "required":"String",
        "show":"String",
      },
      {
        "name":"String",
        "required":"String",
        "show":"String",
      }]
    }
