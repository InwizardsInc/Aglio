# Get Template

This retrieves the definition of the specified template.

## URL

    /accounts/{accountId}/templates/{templateId}

## HTTP Method

    GET

## Parameters

The only required parameter is the template ID.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/templates/{templateId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the template definition of the requested template, along with information about when the template last modified and which user modified the template. Refer to [Post Template](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Post%20Template.htm) for information about the template parameters.

The following example shows the response json body.

### Example Response Body

    {
      "envelopeTemplateDefinition": {
      "templateId": "String content",
      "name": "String content",
      "shared": "String content",
      "password": "String content",
      "description": "String content",
      "lastModified": "String content",
      "lastModifiedBy": {
        "userName": "string",
        "email": "string",
        "userId": "string",
        "uri": "string"
      },
      "pageCount": "String content",
      "folderName": "String content",
      "folderId": "String content",
      "owner": {
        "userName": "String content",
        "email": "String content",
        "userId": "String content",
        "userType": "String content",
        "userStatus": "String content",
      }
      }
      "allowMarkup":"String content",
      "allowReassign":"String content",
      "allowRecipientRecursion":"String content",
      "asynchronous":"String content",
      "authoritativeCopy":""String content",
      "emailBlurb":"String content",
      "emailSubject":"String content",
      "enableWetSign":"String content",
      "enforceSignerVisibility":"String content",
      "signingLocation":"String content",
      "customFields":{
        "listCustomFields":[{
          "name":"String content",
          "required":"String content",
          "show":"String content",
          "value":"String content",
          "listItems":["String content"]
       }],
        "textCustomFields":[{
          "name":"String content",
          "required":"String content",
          "show":"String content",
          "value":"String content",
        }]
      },
      "documents":[{
        "documentId":"String content",
        "fileExtension":"String content",
        "matchBoxes":[{
        }],
        "name":"String content",
        "password":"String content",
        "uri":"String content"
      }],
      "emailBlurb":"String content",
      "emailSubject":"String content",
      "enableWetSign":"String content",
      "enforceSignerVisibility":"String content",
      "eventNotification":{
      },
      "notification":{
        "expirations":{
          "expireAfter":"String content",
          "expireEnabled":"String content",
          "expireWarn":"String content"
        },
        "reminders":{
          "reminderDelay":"String content",
          "reminderEnabled":"String content",
          "reminderFrequency":"String content"
        },
        "useAccountDefaults":"String content"
      },
      "recipients":{
      },
      "signingLocation":"String content",
    }
