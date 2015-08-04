# Get List of Templates used in an Envelope

This returns a list of the templates, name and ID, used in an envelope.

>**Note:** This only returns information for server side templates.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/templates
    Optional addition: include=matching_applied

## HTTP Method

    GET

## Parameters

No additional parameters are required, but the following optional query string can be added to the request.

|Name|Required?|Type|Descripion|
|----|---------|----|----------|
|include|No|String|The possible values are:<br/><ul><li>matching_applied – This returns template matching information for the template.</li></ul>|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/
    envelopes/{envelopeId}/templates?include=matching_applied
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of the templates used in an envelope, showing the name, ID, and uri for the template, along with template matching information if the optional query parameter is included.

The following example shows the response json body with include=matching_applied.

### Example Response Body

    {
      "templates":[
        {
          "templateId":"String content",
          "name":"String content",
          "documentId": "string",
          "documentName": "string",
          "applied": "string",
          "templateMatch": {
            "matchPercentage": "string",
            "documentStartPage": "string",
            "documentEndPage": "string"
          },
          "uri":"String content"
        }
      ]
    }
