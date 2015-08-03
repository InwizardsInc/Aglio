# Remove Envelope Custom Fields from an Envelope

This allows you to remove envelope custom fields for draft and in-process envelopes.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/custom_fields

## HTTP Method

    DELETE

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|listCustomFields|||
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;fieldId|Yes|String|The DocuSign generated ID number for the Envelope Custom Field.|
|textCustomFields|||
|&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;fieldId|Yes|String|The DocuSign generated ID number for the Envelope Custom Field.|

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}
                              /envelopes/{envelopeId}/custom_fields
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json
    {
      "listCustomFields": [{
        "fieldId":"String"
      },
      {
        "fieldId":"String"
      }],
      "textCustomFields": [{
        "fieldId":"String"
      },
      {
        "fieldId":"String"
      }]
    }

## Response

The response returns success or failure and any error messages.
The response also returns the list of envelope custom field IDs that were removed from the envelope.

The following example shows the response json body.

### Example Request Body

    {
      "listCustomFields": [{
        "fieldId":"String"
      },
      {
        "fieldId":"String"
      }],
      "textCustomFields": [{
        "fieldId":"String"
      },
      {
       "fieldId":"String"
      }]
    }
