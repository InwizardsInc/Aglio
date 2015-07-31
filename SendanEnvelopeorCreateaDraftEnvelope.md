# Send an Envelope or Create a Draft Envelope

This creates an envelope and sends it to recipients or saves it as a draft envelope.
Setting the status parameter sets if the envelope is sent or if it is saved to the
draft envelope folder after the request. This is a multipart/form request.

This resource is also used for sending an envelope from a template;
refer to [Send an Envelope from a Template](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Send%20an%20Envelope%20from%20a%20Template.htm) for information about sending from a template.

This resource can also be used with offline signing client applications, see the
[Offline Signing](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Offline%20Signing.htm) section for more information about offline signing.

Envelope Event Notification: eventNotification is an optional element that
specifies a set of envelope and recipient status codes, a URL and some other options.
When the envelope or recipient status changes to one of the specified status codes,
a message containing the updated status is sent to the URL.

>**Note:** DocuSign Connect must be enabled to use eventNotification, but Connect
> does not need to be configured for the account since the configuration is done for each envelope.


**Rules for determining the brandId used in an envelope**

The following rules are used to determine the brandId used in an envelope:

<ul><li>If a brandId is specified in the envelope/template and that brandId is available to the account, that brand is used in the envelope.</li><li>If more than one template is used in an envelope and more than one brandId is specified, the first brandId specified is used throughout the envelope.</li><li>In cases where no brand is specified and the sender belongs to a Group; if there is only one brand associated with the Group, then that brand is used in the envelope. Otherwise, the account’s default signing brand is used.</li><li>For envelopes that do not meet any of the previous rules, the account's default signing brand is used in the envelope.</li></ul>

>**Important:** The BCC Email address feature is designed to provide a copy of all 
> email communications for external archiving purposes. DocuSign recommends that
> envelopes sent using the BCC for Email Archive feature, including the BCC Email Override option,
> include additional signer authentication options. To send a copy of the envelope
> to a recipient who does not need to sign, use a Carbon Copies or Certified Deliveries Recipient Type.

## URL

    /accounts/{accountId}/envelopes

## HTTP Method

    POST

## Parameters

The parameters for sending an envelope are broken down into sections. The parameters used depend on how you are sending the envelope, the recipient types used, and tabs included in the envelope. The parameters listed in this section are: Envelope, [Document](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Document%20Parameters.htm), [Recipient](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Recipient%20Parameter.htm), and [Tab](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Tab%20Parameters.htm).


This section lists the parameters for an envelope.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|accessibility|No|String|An optional element that can only be used if Document Accessibility is enabled for the account. This sets the document reading zones for screen reader applications.<br/><br/>**Note:** This information is currently generated from the DocuSign web console by setting the reading zones when creating a template, exporting the reading zone string information, and adding it here.|
|allowMarkup|No|String|If true, Document Markup is enabled for envelope. Account must have Document Markup enabled to use this.|
|allowReassign|No|String|If true, the recipient can redirect an envelope to a more appropriate recipient.|
|allowRecipientRecursion|No|String|When set to true, this enables the Recursive Recipients feature and allows a recipient to appear more than once in the routing order.|
|asynchronous|No|String|If true, will queue the envelope for processing and the envelope status will have a value of ‘Processing’. Additionally, get status calls will return ‘Processing’ until completed.|
|authoritativeCopy|No|String|Specifies the Authoritative copy feature. If set to true the Authoritative copy feature is enabled.|
|autoNavigation|No|String|If true, auto-navigation is enabled for the envelope. The auto-navigation method used is determined by the account setting.|
|brandId|No|String|This sets the brand profile format used for the envelope. The value in the string is the brandId associated with the profile. Account branding must be enabled for the account to use this option.|
|emailBlurb|No|String|Optional element. This is the same as the email body. If specified it is included in email body for all envelope recipients. This can be a maximum of 10000 characters.|
|emailSubject|Yes|String|The subject of the email that will be sent to all recipients. This can be a maximum of 100 characters.|
|enableWetSign|No|String|If true, the signer is allowed to print the document and sign it on paper.|
|enforceSignerVisibility|No|String|It true, the signer is required to have a signature or initial tab on the document or that the document has no signers in order to view it. Account must have Document Visibility enabled to use this|
|envelopeIdStamping|No|String|If true, Envelope ID Stamping is enabled.|
|messageLock|No|String|If true, prevents senders from changing the emailBlurb and emailSubject for the envelope.<br/>Additionally, this prevents users from making changes to the emailBlurb and emailSubject when correcting envelopes<br/>However, if the messageLock node is set to True and the emailSubject is empty, senders and correctors are able to add a subject to the envelope.|
|notification|No||An optional complex element that specifies the notification options for the envelope. It consists of:<br/><br/><ul><li>useAccountDefaults – When true, the account default notification settings are used for the envelope.</li><li>reminders – A complex element that specifies reminder settings for the envelope. It consists of:<br/><ul><li>reminderEnabled – When true the envelope expires (is no longer available for signing) in the set number of days. If false, the account default setting is used. If the account does not have an expiration setting, the DocuSign default value of 120 days is used.</li><li>reminderDelay – An interger that sets the number of days after the recipient receives the envelope that reminder emails are sent to the recipient.</li><li>reminderFrequency – An interger that sets the interval, in days, between reminder emails.</li></ul></li><li>expirations – A complex element that specifies the expiration settings for the envelope. It consists of:<br/><ul><li>expireEnabled – When true the envelope expires (is no longer available for signing) in the set number of days. If false, the account default setting is used. If the account does not have an expiration setting, the DocuSign default value of 120 days is used.</li><li>expireAfter – An integer that sets the number of days the envelope is active.</li><li>expireWarn – An integer that sets the number of days before envelope expiration that an expiration warning email is sent to the recipient. If set to 0 (zero), no warning email is sent.</li></ul></li></ul>|
|recipientsLock|No|String|If true, prevents senders from changing, correcting, or deleting the recipient information for the envelope.|
|signingLocation|No|String|Specifies the physical location where the signing takes place. It can have two enumeration values; InPerson and Online. The default value is Online.|
|status|Yes|String|Sets envelope status. There are two possible values: sent and created.<br/>If status = sent, the envelope is sent to the recipients.<br/>If status = created, the envelope is saved as a draft and can be modified and sent later.|
|transactionId|No|String|An optional element that can be used to identify an envelope. The id is a sender-generated value and is valid in the DocuSign system for 7 days.<br/>It is recommended that a transactionId is used for offline signing to ensure that an envelope is not sent multiple times.<br/>The transactionId can be used determine if an envelope status (i.e. was created or not) for cases where an internet connection was lost before the envelope status could be returned.|
|useDisclosure|No|Boolean|When set to ‘false’, the Electronic Record and Signature Disclosure is not shown to any envelope recipients. When set to ‘true’, the disclosure is shown to recipients in accordance with the account’s Electronic Record and Signature Disclosure frequency setting. If there is no setting for use useDisclosure, then the account’s normal disclosure setting is used and the useDisclosure setting is not returned in responses when getting envelope information.|
|customFields|No||A complex element that can be used to record information about the envelope, help search for envelopes and track information.<br/>**Note:** Each custom field used in an envelope must have a unique name.<br/>See the section on [getting Custom Fields](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Get%20Envelope%20Custom%20Field%20Information.htm) for more information about and descriptions of the custom fields.|
|documents|No|Document|Complex element contains the details on the documents in the envelope.<br/> See the [Document parameter](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Document%20Parameters.htm) section for more information.|
|recipients|No|Recipient|Specifies the envelope recipients.<br/>See the [Recipient parameter](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Recipient%20Parameter.htm) section for more information.|
|eventNotification|No|EventNotification|This optional complex element allows a message to be sent a specified URL when the envelope or recipient changes status. It is similar to DocuSign Connect. For example, if an envelope changes from "Sent" to "Delivered", a message containing the updated envelope status and optionally the documents is sent to the URL.<br/>When an eventNotification is attached to an envelope using the API, it only applies to the envelope (treating the envelope as the sender). This is different from envelopes created through the console user interface, where the user is treated as the sender.<br/>eventNotification consists of:<br/><ul><li>url – The endpoint where envelope updates are sent. This will accept XML unless “useSoapInterface” is set to true.</li><li>loggingEnabled – When set to true, logging is turned on for envelope events on the Web Console Connect page.</li><li>requireAcknowledgment – When set to true, the DocuSign Connect service checks that the message was received and retries on failures.</li><li>useSoapInterface – When set to true, this tells the Connect service that the user’s endpoint has implemented a SOAP interface.</li><li>soapNameSpace – This lists the namespace in the SOAP listener provided.</li><li>includeCertificateWithSoap – When set to true, this tells the Connect service to send the DocuSign signedby certificate as part of the outgoing SOAP xml. This appears in the XML as wsse:BinarySecurityToken.</li><li>signMessageWithX509Cert – When set to true, messages are signed with an X509 certificate. This provides support for 2-way SSL in the envelope.</li><li>includeDocuments – When set to true, the PDF documents are included in the message along with the updated XML.</li><li>includeEnvelopeVoidReason – When set to true, this tells the Connect Service to include the void reason, as entered by the person that voided the envelope, in the message.</li><li>includeTimeZone – When set to true, the envelope time zone information is included in the message</li><li>includeSenderAccountAsCustomField – When set to true, the sender account ID is included as a envelope custom field in the data.</li><li>includeDocumentFields – When set to true, this tells the Connect Service to include the Document Fields associated with the envelope. Document Fields are optional custom name-value pairs added to documents using the API.</li><li>includeCertificateOfCompletion – When set to true, this tells the Connect Service to include the Certificate of Completion with completed envelopes.</li><li>envelopeEvents – The list of envelope-level events statuses that will trigger Connect to send updates to the url. It can be a two-part list with:<ul><li>envelopeEventStatusCode – The envelope status, this can be Sent, Delivered, Completed, Declined, or Voided.</li><li>includeDocuments – When set to true, the envelope time zone information is included in the message.</li></ul></li><li>recipientEvents – The list of recipient event statuses that will trigger Connect to send updates to the url. It can be a two-part list with:<ul><li>recipientEventStatusCode – The recipient status, this can be Sent, Delivered, Completed, Declined, AuthenticationFailed, and AutoResponded.</li><li>includeDocuments – When set to true, the envelope time zone information is included in the message.</li></ul></li></ul>.|
|emailSettings|No|emailSettings|This optional complex element allows sender to override some envelope email setting information. This can be used to override the Reply To email address and name associated with the envelope and to override the BCC email addresses to which an envelope is sent.<br/>When the emailSettings information is used for an envelope, it only applies to that envelope.<br/>**IMPORTANT:**  The emailSettings information is not returned in the GET for envelope status. Use [GET /email_settings](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Get%20Email%20Setting%20Overrides%20for%20an%20Envelope.htm) to return information about the emailSettings.<br/>EmailSettings consists of:<br/><ul><li>replyEmailAddressOverride – The Reply To email used for the envelope. DocuSign will verify a correct email format is used, but does not verify that the email is active. This can be a maximum of 100 characters.</li><li>replyEmailNameOverride – The name associated with the Reply To email address. This can be a maximum of 100 characters.</li><li>bccEmailAddresses – Only users with canManageAccount setting can use this option. This is an array of up to 5 email addresses the envelope is sent to as a BCC email.<br/>email – The BCC email address. DocuSign verifies that the email format is correct, but does not verify that the email is active. This can be a maximum of 100 characters. Using this overrides the BCC for Email Archive information setting for this envelope.<br/>**Example:** if your account has BCC for Email Archive set up for the email address ‘archive@mycompany.com’ and you send an envelope using the BCC Email Override to send a BCC email to ‘salesarchive@mycompany.com’, then a copy of the envelope is only sent to the ‘salesarchive@mycompany.com’ email address.</li></ul>|

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: multipart/form-data; boundary=AAA
    
    --AAA
    Content-Type: application/json
    Content-Disposition: form-data
    {
      "accessibility":"string content",
      "allowMarkup":"String content",
      "allowReassign":"String content",
      "allowRecipientRecursion":"String content",
      "asynchronous":"String content",
      "authoritativeCopy":"String content",
      "autoNavigation":"String content",
      "brandId":"String content",
      "emailBlurb":"String content",
      "emailSubject":"String content",
      "enableWetSign":"String content",
      "enforceSignerVisibility":"String content",
      "envelopeIdStamping":"String content",
      "messageLock":"string content",
      "notification":{
        "useAccountDefaults":"String content",
         "reminders":{
            "reminderEnabled":"String content",
            "reminderDelay":"String content",
            "reminderFrequency":"String content"
       },
      "expirations":{
        "expireEnabled":"String content",
        "expireAfter":"String content",
        "expireWarn":"String content"
      }
      },
      "recipientsLock":"String content",
      "signingLocation":"String content",
      "status":"String content",
      "transactionId":"String content",
      "useDisclosure":"String",
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
        "value":"String content"
      }]
      },
      "documents": [{
        "documentId":"1",
        "name":"string",
        "remoteUrl": "string"
        "documentFields": [{
          "name": "string",
          "value": "string"
        },
        {
          "name": "string",
          "value": "string"
        }],
      "encryptedWithKeyManager":"String Content",
      "transformPdfFields":"String Content",
      "order":"String Content",
      "pages":"String Content",
      "fileExtension":"String Content",
      "documentBase64":"String Content",
      "matchboxes": [{
          "pageNumber": "string",
          "xPosition": "string",
          "yPosition": "string",
          "width": "string",
          "height": "string"
        },
        {
          "pageNumber": "string",
          "xPosition": "string",
          "yPosition": "string",
          "width": "string",
          "height": "string"
        }],
      }],
      "recipients": {
        "signers" : [{
          "email":"String content",
          "name":"String content",
          "recipientId":"1"
       }],
      "eventNotification":{
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
