# Modify a Template

This allows users to modify an existing template.

## URL

    /accounts/{accountId}/templates/{templateId}

## HTTP Method

    PUT

## Parameters

This uses the same parameters as creating a new template, but only the parameters being changed are required. Refer to [Post Template](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Post%20Template.htm) for information about the template parameters.

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/templates/{templateid}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: multipart/form-data; boundary=AAA
    
    --AAA
    Content-Type: application/json
    Content-Disposition: form-data
    
    {
      "envelopeTemplateDefinition": {
        "templateId": "String content",
        "name": "String content",
        "shared": "String content",
        "password": "String content",
        "description": "String content",
        "lastModified": "String content",
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
      "accessibility":"string content",
      "allowMarkup":"String content",
      "allowReassign":"String content",
      "allowRecipientRecursion":"String content",
      "asynchronous":"String content",
      "authoritativeCopy":""String content",
      "autoNavigation":"String content",
      "brandId":"String content",
      "emailBlurb":"String content",
      "emailSubject":"String content",
      "enableWetSign":"String content",
      "enforceSignerVisibility":"String content",
      "envelopeIdStamping":"String content",
      "messageLock":"string content",
      "recipientsLock":"String content",
      "signingLocation":"String content",
      "eventNotification":{  "customFields":{
        "url":"String content",
        "loggingEnabled":"String content",
        "requireAcknowledgment":"String content",
        "useSoapInterface":"String content",
        "soapNameSpace" : "http://DocuSignConnectListener",
        "includeCertificateWithSoap" : "true",
        "envelopeEvents" : [{
          "envelopeEventStatusCode" : "sent"
        },
        {
          "envelopeEventStatusCode" : "completed",
          "includeDocuments" : "true"
        }]
      }]
      "customFields":[{
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
      "notification": {
        "useAccountDefaults": "sample string 1",
        "reminders": {
          "reminderEnabled": "sample string 1",
          "reminderDelay": "sample string 2",
          "reminderFrequency": "sample string 3"
        },
        "expirations": {
          "expireEnabled": "sample string 1",
          "expireAfter": "sample string 2",
          "expireWarn": "sample string 3"
        }
      },
      "documents": [{
      }],
      "emailBlurb": "Envelope Template Test email Blurb",
      "emailSubject": "Envelope Template test Email Subject",
      },
      "recipients": {
    "signers": [{
      "accessCode": "",
      "addAccessCodeToEmail": false,
      "clientUserId": null,
      "customFields": null,
      "emailNotification": null,
      "idCheckConfigurationName": null,
      "idCheckInformationInput": null,
      "inheritEmailNotificationConfiguration": false,
      "note": "",
      "phoneAuthentication": null,
      "recipientAttachments": null,
      "recipientId": "1",
      "requireIdLookup": false,
      "roleName": "Signer 1",
      "routingOrder": 1,
      "socialAuthentications": null,
      "templateAccessCodeRequired": false,
      "templateLocked": false,
      "templateRequired": false,
      "email": "",
      "name": "",
      "autoNavigation": false,
      "defaultRecipient": false,
      "signatureInfo": null,
      "tabs": {
        "approveTabs": null,
        "checkboxTabs": null,
        "companyTabs": null,
        "dateSignedTabs": null,
        "dateTabs": null,
        "declineTabs": null,
        "emailTabs": null,
        "envelopeIdTabs": null,
        "fullNameTabs": null,
        "initialHereTabs": null,
        "listTabs": null,
        "noteTabs": null,
        "numberTabs": null,
        "radioGroupTabs": null,
        "signHereTabs": [{
           "anchorString": null,
           "anchorXOffset": null,
           "anchorYOffset": null,
           "anchorignoreIfNotPresent": null,
           "anchorUnits": null,
           "conditionalParentLabel": null,
           "conditionalParentValue": null,
           "documentId": "1",
           "pageNumber": "1",
           "recipientId": "1",
           "templateLocked": false,
           "templateRequired": false,
           "xPosition": "157",
           "yPosition": "7",
           "name": "Sign Here",
           "optional": false,
           "scaleValue": 1,
           "tabLabel": "Signature 1"
        }],
        "signerAttachmentTabs": null,
        "ssnTabs": null,
        "textTabs": null,
        "titleTabs": null,
        "zipTabs": null
      }
    },
    {
      "accessCode": "",
      "addAccessCodeToEmail": false,
      "customFields": null,
      "emailNotification": null,
      "idCheckConfigurationName": null,
      "idCheckInformationInput": null,
      "inheritEmailNotificationConfiguration": false,
      "note": "",
      "phoneAuthentication": null,
      "recipientAttachments": null,
      "recipientCaptiveInfo": null,
      "recipientId": "2",
      "requireIdLookup": false,
      "roleName": "Signer 2",
      "routingOrder": 1,
      "socialAuthentications": null,
      "templateAccessCodeRequired": false,
      "templateLocked": false,
      "templateRequired": false,
      "email": "",
      "name": "",
      "autoNavigation": false,
      "defaultRecipient": false,
      "signatureInfo": null,
      "tabs": {
        "approveTabs": null,
        "checkboxTabs": null,
        "companyTabs": null,
        "dateSignedTabs": null,
        "dateTabs": null,
        "declineTabs": null,
        "emailTabs": null,
        "envelopeIdTabs": null,
        "fullNameTabs": null,
        "initialHereTabs": null,
        "listTabs": null,
        "noteTabs": null,
        "numberTabs": null,
        "radioGroupTabs": null,
        "signHereTabs": [{
           "anchorString": null,
           "anchorXOffset": null,
           "anchorYOffset": null,
           "anchorignoreIfNotPresent": null,
           "anchorUnits": null,
           "conditionalParentLabel": null,
           "conditionalParentValue": null,
           "documentId": "1",
           "pageNumber": "1",
           "recipientId": "2",
           "templateLocked": false,
           "templateRequired": false,
           "xPosition": "351",
           "yPosition": "12",
           "name": "Sign Here",
           "optional": false,
           "scaleValue": 1,
           "tabLabel": "Signature 2"
        }],
        "signerAttachmentTabs": null,
        "ssnTabs": null,
        "textTabs": null,
        "titleTabs": null,
        "zipTabs": null
      }
    }]
    }
    }
    
    --AAA
    Content-Type: application/pdf
    Content-Disposition: file; filename="test1.pdf"; documentId=1
    
    <PDF Bytes Removed>

## Response

The response returns success or failure and the template information.

The following example shows the header followed by the response json body.

### Example Response Body

    {
      "name":"String content",
      "templateId":"String content",
      "uri":"String content"
    }
