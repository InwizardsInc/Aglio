# Post Template

Saves a template definition using a multipart request.

## URL

    /accounts/{accountId}/templates

## HTTP Method

    POST

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|accessibility|No|String|An optional element that can only be used if Document Accessibility is enabled for the account. This sets the document reading zones for screen reader applications.<br/><br/>**Note:** This information is currently generated from the DocuSign web console by setting the reading zones when creating a template, exporting the reading zone string information, and adding it here.|
|allowMarkup|No|String|If true, Document Markup is enabled for envelope. Account must have Document Markup enabled to use this.|
|allowReassign|No|String|If true, the recipient can redirect an envelope to a more appropriate recipient.|
|allowRecipientRecursion|No|String|When set to true, this enables the Recursive Recipients feature and allows a recipient to appear more than once in the routing order.|
|asynchronous|No|String|If true, will queue the envelope for processing and EnvelopeStatus will have a value of ‘Processing’. Use SynchEnvelope to determine when the queued envelope has been processed. Additionally, RequestStatus calls will return ‘Processing’ until completed.|
|authoritativeCopy|No|String|Specifies the Authoritative copy feature. If set to true the Authoritative copy feature is enabled.|
|autoNavigation|No|string|If true, auto-navigation is enabled for the envelope. The auto-navigation method used is determined by the account setting.|
|brandId|No|String|This sets the brand profile format used for the envelope. The value in the string is the brandId associated with the profile. Account branding must be enabled for the account to use this option.|
|emailBlurb|No|String|Optional element.This is the same as the email body. If specified it is included in email body for all envelope recipients.|
|emailsubject|Yes|String|The subject of the email that will be sent to all recipients.|
|enableWetSign|No|String|If true, the signer is allowed to print the document and sign it on paper.|
|enforceSignerVisibility|No|String|It true, the signer is required to have a signature or initial tab on the document or that the document has no signers in order to view it. Account must have Document Visibility enabled to use this.|
|envelopeIdStamping|No|String|If true, Envelope ID Stamping is enabled.|
|eventNotification|No|Event Notification|This optional complex element allows a message to be sent a specified URL when the envelope or recipient changes status. It is similar to DocuSign Connect. For example, if an envelope changes from "Sent" to "Delivered", a message containing the updated envelope status and optionally the documents is sent to the URL.<br/>When an eventNotification is attached to an envelope using the API, it only applies to the envelope (treating the envelope as the sender). This is different from envelopes created through the console user interface, where the user is treated as the sender.<br/>eventNotification consists of:<br/><ul><li>url – The endpoint where envelope updates are sent. This will accept XML unless “useSoapInterface” is set to true.</li><li>loggingEnabled – When set to true, logging is turned on for envelope events on the Web Console Connect page.</li><li>requireAcknowledgment – When set to true, the DocuSign Connect service checks that the message was received and retries on failures.</li><li>useSoapInterface – When set to true, this tells the Connect service that the user’s endpoint has implemented a SOAP interface.</li><li>soapNameSpace – This lists the namespace in the SOAP listener provided.</li><li>includeCertificateWithSoap – When set to true, this tells the Connect service to send the DocuSign signedby certificate as part of the outgoing SOAP xml. This appears in the XML as wsse:BinarySecurityToken.</li><li>signMessageWithX509Cert – When set to true, messages are signed with an X509 certificate. This provides support for 2-way SSL in the envelope.</li><li>includeDocuments – When set to true, the PDF documents are included in the message along with the updated XML.</li><li>includeEnvelopeVoidReason – When set to true, this tells the Connect Service to include the void reason, as entered by the person that voided the envelope, in the message.</li><li>includeTimeZone – When set to true, the envelope time zone information is included in the message.</li><li>includeSenderAccountAsCustomField – When set to true, the sender account ID is included as a envelope custom field in the data.</li><li>includeDocumentFields – When set to true, this tells the Connect Service to include the Document Fields associated with the envelope. Document Fields are optional custom name-value pairs added to documents using the API.</li><li>includeCertificateOfCompletion – When set to true, this tells the Connect Service to include the Certificate of Completion with completed envelopes.</li><li>envelopeEvents – The list of envelope-level events statuses that will trigger Connect to send updates to the url. It can be a two-part list with:<br/><ul><li>envelopeEventStatusCode – The envelope status, this can be Sent, Delivered, Completed, Declined, or Voided.</li><li>includeDocuments – When set to true, the envelope time zone information is included in the message.</li></ul></li><li>recipientEvents – The list of recipient event statuses that will trigger Connect to send updates to the url. It can be a two-part list with:<br/><ul><li>recipientEventStatusCode – The recipient status, this can be Sent, Delivered, Completed, Declined, AuthenticationFailed, and AutoResponded.</li><li>includeDocuments – When set to true, the envelope time zone information is included in the message.</li></ul></li></ul>|
|messageLock|No|String|If true, prevents senders from changing the emailBlurb and emailSubject for the envelope.<br/>Additionally, this prevents users from making changes to the emailBlurb and emailSubject when correcting envelopes<br/>However, if the messageLock node is set to True and the emailSubject is empty, senders and correctors are able to add a subject to the envelope.|
|recipientsLock|No|String|If true, prevents senders from changing, correcting, or deleting the recipient information for the envelope.|
|signingLocation|No|String|Specifies the physical location where the signing takes place. It can have two enumeration values; InPerson and Online. The default value is Online.|
|customFields|No||customFields are part of the json structure, but they are ignored when Posting. They are set in the console.|
|documents|Yes|Document|Complex element contains the details on the documents in the envelope.<br/>See the [Document parameter](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Document%20Parameters.htm) section for more information.|
|recipients|Yes|Recipient|Specifies the envelope recipients. It uses the same information as a standard envelope recipient, with the following exceptions:<br/><ul><li>The email and name elements are not required.</li><li>The roleName element is required. This can be a maximum of 100 characters.</li></ul>See the [Recipient parameter](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Recipient%20Parameter.htm) sections for more information.|
|envelopeTemplateDefinition|Yes||A complex element with the following information:<br/>templateId: Unique identifier of the template. If this is not provided, DocuSign will generate a value.<br/>name: Name of the template. This can be a maximum of 100 characters.<br/>shared: If true, the template is shared with the Everyone group in the account. If false, the template is only shared with the Administrator group.<br/>password: Password, if the template is locked.<br/>description: Description of the template. This can be a maximum of 500 characters.<br/>pageCount: Number of document pages in the template.<br/>folderName: The name of the folder the template is located in.<br/>folderId: The ID for the folder.<br/>owner: The userName, email, userId, userType, and userStatus for the template owner.|
|notification|No||An optional complex element that specifies the notification options for the envelope. It consists of:<br/><ul><li>useAccountDefaults – When true, the account default notification settings are used for the envelope.</li><li>reminders – A complex element that specifies reminder settings for the envelope. It consists of:<ul><li>reminderEnabled – When true a reminder message is sent to the recipient.</li><li>reminderDelay – An interger that sets the number of days after the recipient receives the envelope that reminder emails are sent to the recipient.</li><li>reminderFrequency – An interger that sets the interval, in days, between reminder emails.</li></ul></li><li>expirations – A complex element that specifies the expiration settings for the envelope. It consists of:<ul><li>expireEnabled – When true the envelope expires (is no longer available for signing) in the set number of days. If false, the account default setting is used. If the account does not have an expiration setting, the DocuSign default value of 120 days is used.</li><li>expireAfter – An integer that sets the number of days the envelope is active.</li><li>expireWarn – An integer that sets the number of days before envelope expiration that an expiration warning email is sent to the recipient. If set to 0 (zero), no warning email is sent.</li></ul></li></ul>|

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/templates
    
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
        "signMessageWithX509Cert":"String content",
        "includeDocuments":"String content",
        "includeEnvelopeVoidReason": "String content",
        "includeTimeZone" : "http://DocuSignConnectListener",
        "includeSenderAccountAsCustomField" : "true",
        "includeDocumentFields": "String content",
        "includeCertificateOfCompletion": "String content",
        "envelopeEvents": [{
          "envelopeEventStatusCode" : "sent"
        },
        {
          "envelopeEventStatusCode" : "completed",
          "includeDocuments":"true"
        }],
        "recipientEvents":[{
          "recipientEventStatusCode":"Sent"
        },
        {
          "recipientEventStatusCode":"completed",
          "includeDocuments":"true"
        }]
      },
      "emailSettings": {
        "replyEmailAddressOverride": "string",
        "replyEmailNameOverride": "string",
        "bccEmailAddresses": [
          {
            "email": "string"
          },
          {
            "email": "string"
          }
        ]
      }
      }
      
      --AAA
      Content-Disposition:documentId=1
      
      <bytes of PDF removed>
      
      --AAA--
      "envelopeEvents" : [
        {
            "envelopeEventStatusCode" : "sent"
        },
        {
          "envelopeEventStatusCode" : "completed",
          "includeDocuments" : "true"
        }
      ],
      "recipientEvents" : [
        {
          "recipientEventStatusCode" : "Sent"
        },
        {
          "recipientEventStatusCode" : "completed",
          "includeDocuments" : "true"
        }
      ]
    },
    "emailSettings": {
      "replyEmailAddressOverride": "string",
      "replyEmailNameOverride": "string",
      "bccEmailAddresses": [
        {
          "email": "string"
        },
        {
          "email": "string"
        }
      ]
    },
    "compositeTemplates":[
      {
        "compositeTemplateId":"String content",
        "serverTemplates":[
          {
            "sequence":"String content",
            "templateId":"String content"
          },
          {
            "sequence":"String content",
            "templateId":"String content"
          }
        ],
      "inlineTemplates":[
        {
          "sequence":"String content",
          "documents":[
            {
              "documentId":"String content",
              "name":"String content",
              "transformPdfFields":"String"
            },
            {
              "documentId":"String content",
              "name":"String content",
              "transformPdfFields":"String"
            }
          ]
        }
      ],
      "pdfMetaDataTemplateSequence":"String content",
      "document" : [
        {
          "documentId" : "string",
          "documentBase64": "string" 
        }
      ]
      }
    ]
    }
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

The response returns the template name, template ID and template uri.

The following example shows the header followed by the response json body.

### Example Response Body

    {
      "name":"String content",
      "templateId":"String content",
      "uri":"String content"
    }
