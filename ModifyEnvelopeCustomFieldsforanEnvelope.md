# Modify Envelope Custom Fields for an Envelope

This allows you to edit the envelope custom fields for draft and in-process envelopes.

>**Note:** Each custom field used in an envelope must have a unique name.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/custom_fields

## HTTP Method

    PUT

## Parameters

The parameters for an Envelope Custom Field are only required if you are editing that custom field.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|listCustomFields|||
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;fieldId|Yes|String|The DocuSign generated ID number for the Envelope Custom Field.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;name|Yes|String|The name of the Envelope Custom Field. This can be a maximum of 50 characters.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;required|Yes|String|When true, information must be entered into the custom field to send the envelope.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;show|Yes|String|When true, the custom field is shown to senders in the DocuSign member console during sending.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;value|Yes|String|The selected value for the field. This can be a maximum of 100 characters.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;listItems|Yes|String|The list of values that can be selected by senders. The list values are separated by semi-colons. Example: [one;two;three;four]<br/><br/>This can be a maximum of 2048 characters, but each value can only be a maximum of 100 characters.|
|textCustomFields|||
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;fieldId|Yes|String|The DocuSign generated ID number for the Envelope Custom Field.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;name|Yes|String|The name of the Envelope Custom Field. This can be a maximum of 50 characters.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;required|Yes|String|When true, information must be entered into the custom field to send the envelope.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;show|Yes|String|When true, the custom field is shown to senders in the DocuSign member console during sending.|
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;value|Yes|String|The entered value for the field. This can be a maximum of 100 characters.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/
                                envelopes/{envelopeId}/custom_fields
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>
                               {integrator_key}</IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json
    
    {
      "listCustomFields": [{
        "fieldId": "String content",
        "name":"String",
        "required":"String",
        "show":"String",
        "value":"String",
        "listItems": ["String","String"]
      },
      {
        "fieldId": "String content",
        "name":"String",
        "required":"String",
        "show":"String",
        "value":"String",
        "listItems": ["String","String"]
      }],
      "textCustomFields": [{
        "fieldId": "String content",
        "name":"String",
        "required":"String",
        "show":"String",
        "value":"String"
      },
      {
        "fieldId": "String content",
        "name":"String",
        "required":"String",
        "show":"String",
        "value":"String"
      }]
    }
  
## Response
  
The response returns success or failure and any error messages. The response also returns the list of envelope custom fields with the updated values.

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
      },
      {
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
      },
      {
        "fieldId": "String content",
        "name": "String content",
        "required": "String content",
        "show": "String content",
        "value":"String content"
      }]
    }
