# Add User to Account

This adds new users to your account.

## URL

    /accounts/{accountId}/users

## HTTP Method

    POST

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|activationAccessCode|No|String|The activation code the new user must enter when activating their account.|
|email|Yes|String|The user’s email address for the associated account. This can be a maximum of 100 characters.|
|enableConnectForUser|No|String|Sets if the user is enabled for updates from DocuSign Connect. This is a true/false setting.|
|firstName|No|String|The user’s first name. This can be a maximum of 50 characters.|
|forgottenPasswordInfo|No||A complex element that has up to four Question/Answer pairs for forgotten password information.|
|groupList|No|String|A list of the group information for groups to add the user to. Group information can be found by using [GET group information](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Get%20Group%20Information.htm). Only the groupId is required. The parameters are:<br/><ul><li>groupId – The DocuSign group ID for the group.</li><li>groupName – The name of the group.</li><li>permissionProfileId – The ID of the permission profile associated with the group.</li><li>groupType – The group type.</li></ul>|
|lastName|No|String|The user’s last name. This can be a maximum of 50 characters.|
|middleName|No|String|The user’s middle name. This can be a maximum of 50 characters.|
|password|No|String|The user’s password for the associated account. This can be a maximum of 50 characters.|
|sendActivationOnInvalidLogin|No|String|Sets if another activation email is sent to the user if the fail a log on before activating their account. This is a true/false setting.|
|suffixName|No|String|The suffix for the user’s name. This can be a maximum of 50 characters.|
|title|No|String|The suffix for the user’s name. This can be a maximum of 50 characters.|
|title|No|String|The user’s title. This can be a maximum of 50 characters.|
|userName|Yes|String|The full user name associated with the account. This can be a maximum of 100 characters.|
|userSettings|No||The name/value pair information for user settings. These determine the actions that a user can take in the account. The [userSettings](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Add%20User%20to%20Account.htm#userSett) are listed and described below.|


userSettings

|Name|Value|Authorization Requried|Description|
|----|-----|----------------------|-----------|
|allowBulkRecipients|Boolean|Admin|When true, this user can use the bulk send functionality.|
|allowRecipientLanguageSelection|Boolean|Admin|When true, this provides the sender with the option to set the language used in the standard email format for a recipient when creating an envelope.|
|allowSendOnBehalfOf|Boolean|Admin|When true, this user can send and manage envelopes for the entire account using the DocuSign API.|
|canEditSharedAddressBook|String|Admin|This element sets the address book usage and management rights for the user.<br/><br/>Enumeration values are: None, UseOnlyShared, UsePrivateAndShared, Share.|
|canManageAccount|Boolean|Admin & not setting for self|When true, this user can manage account settings, manage user settings, add users, and remove users.|
|canManageTemplates|String|Admin & not setting for self|This element sets the template usage and management rights for the user.<br/><br/>Enumeration values are: None, Use, Create, Share.|
|canSendAPIRequests|Boolean|Admin & Account:UsesAPI is set|Only needed if Integrator Key is not used. When true, this user can send and manage envelopes using the DocuSign API.|
|canSendEnvelope|Boolean|Admin & not setting for self|When true, this user can send envelopes though the DocuSign Console.|
|enableDSPro|Boolean|SysAdmin|When true, this user can send and manage envelopes from the DocuSign Desktop Client.|
|enableSequentialSigningAPI|Boolean|SysAdmin|When true, this user can define the routing order of recipients for envelopes sent using the DocuSign API.|
|enableSequentialSigningUI|Boolean|SysAdmin|When true, this user can define the routing order of recipients while sending documents for signature.|
|enableSignerAttachments|Boolean|Admin|When true, this user can add requests for attachments from signers while sending documents.|
|enableSignOnPaperOverride|Boolean|Admin|When true, this user can override the account setting that determines if signers may sign their documents on paper as an option to signing electronically.|
|enableTransactionPoint|Boolean|SysAdmin|When true, this user can select an envelope from their member console and upload the envelope documents to TransactionPoint.|
|enableVaulting|Boolean|Admin|When true, this user can use electronic vaulting for documents.|
|locale|String|Admin|This sets the default language for the user. The supported languages, with the language value shown in parenthesis are: Chinese Simplified (zh_CN), Chinese Traditional (zh_TW), Dutch (nl), English US (en), French (fr), German (de), Italian (it), Japanese (ja), Korean (ko), Portuguese (pt), Portuguese (Brazil) (pt_BR), Russian (ru), Spanish - (es).|
|powerFormAdmin|Boolean|Admin|When true, this user can create, manage and download the PowerForms documents.|
|powerFormUser|Boolean|Admin|When true, this user can view and download PowerForms documents.|
|selfSignedRecipientEmailDocument|String|Admin|This sets the user setting for how self-signed documents are presented to the email recipients. This will override the account setting. This can only be changed if the selfSignedRecipientEmail DocumentUserOverride accountSetting is true. Enumeration values are:<ul><li>include_pdf: With this setting a PDF of the completed document is attached to the email</li><li>include_link: With this setting a secure link to the self-signed documents is included in the email.</li></ul>|
|vaultingMode|String|Admin|This element sets the electronic vaulting mode for the user.<br/>Enumeration values are: None, eStored and electronicOriginal.|

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/users
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "newUsers":[{
        "activationAccessCode":"String content",
        "email":"String content",
        "enableConnectForUser":"String content",
        "firstName":"String content",
        "forgottenPasswordInfo":{
          "forgottenPasswordAnswer1":"String content",
          "forgottenPasswordAnswer2":"String content",
          "forgottenPasswordAnswer3":"String content",
          "forgottenPasswordAnswer4":"String content",
          "forgottenPasswordQuestion1":"String content",
          "forgottenPasswordQuestion2":"String content",
          "forgottenPasswordQuestion3":"String content",
          "forgottenPasswordQuestion4":"String content"
        },
        "groupList": [
          {
            "groupId": "string content",
           "groupName": "string content",
            "permissionProfileId": "string content",
            "groupType": "string content"
          },
          {
            "groupId": "string content",
            "groupName": "string content",
            "permissionProfileId": "string content",
            "groupType": "string content"
          }
        ],
        "lastName":"String content",
        "middleName":"String content",
        "password":"String content",
        "sendActivationOnInvalidLogin":"String content",
        "suffixName":"String content",
        "title":"String content",
        "userName":"String content",
        "userSettings":[{
          "name":"String content",
          "value":"String content"
        }]
      }]
    }

## Response

The response returns the new user’s information.

The following example shows the response json body.

### Example Response Body

    {
      "newUsers":[
        {
          "userId":"String content",
          "uri":"String content",
          "apiPassword":"String content",
          "email":"String content",
          "userName":"String content",
          "errorDetails":{
            "errorCode":"String content",
            "message":"String content"
          }
        }
      ]
    }
