# Create Account

This creates a new account for using the DocuSign service.

## URL:

    /accounts

## Formats:

    XML, JSON

## HTTP Method:

    POST

## Parameters: 

|Name|Required?|Type|Description|
|--------------------|---------|-------------|-------------------------------------------------------|
|accountName|Yes|String|The account name for the new account.|
|accountSetting|No||The nam/value pair information for [account setting](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Create%20Account.htm#accountS). These determine the features available for the account. The accountSetting are listed and described below.|
|addressInformation|No|String|A complex type that contains following for the new account (all string content): address1, address2, cuty, country , fax, phone , psotalCode and state.<br/>**Note:** If country is US(United States) then States codes are validated for US States. Otherwise state is treated as non-validated string and serves the puppose of entering a state/province/region<br/>The maximum charecters of the string are:<br/> <ul><li>address1, address2, city, country and state: 100 characters</li><li>postalCode, phone, and fax: 20 characters</li><ul/>|
|creditCardInformation|No|String|A complex type that has information about the credit card used to pay for this account. It included the elements: cardNumber, cardType, expirationMonth, expirationYear and nameOnCard.|
|distributorCode|Yes|String|The Distributor Code that identifies the billing plan groups and plans for the new account.|
|distributorPassword|Yes|String|The Distributor Password for the distributorCode.|
|initialUser|Yes||A complex type with the initial user information for the new account. [See Add User To Account](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Add%20User%20to%20Account.htm) for more information on the settings needed for a user.|
|planInformation<br/>currencyCode|Yes||This is the ISO currency code for the account.|
|planInformation<br/>planFeatureSets|No||A complex type that sets the feature sets for the account. It contains the following information (all string content):<br/><ul><li>currencyFeatureSetPrices - This contains the currencyCode and currencySymbol for the alternate currency values for envelopeFee, fixedFee, seatFee that are configured for this plan feature set.</li><li>envelopeFee - An incremental envelope cost for plans with envelope overages (when isEnabled=true).</li><li>featureSetId - A unique ID for the feature set.</li><li>fixedFee - A one-time fee associated with the plan (when isEnabled=true).</li><li>isActive - Determines if the feature set is actively set as part of the plan.</li><li>isEnabled - Determines if the feature set is actively enabled as part of the plan.</li><li>name - The name of the feature set.</li><li>seatFee - An incremental seat cost for seat-based plans (when isEnabled=true).</li></ul>|
|planInformation<br/>planId|Yes|String|The DocuSign Plan ID for the account.|
|planInformation<br/>freeTrialDaysOverride|No|String|Reserved for DocuSign use only.|
referralInformation|No||A complex type that contains the following information for entering referral and discount information. The following items are included in the referral information (all string content): enableSupport, includedSeats, saleDiscountPercent, saleDiscountAmount, saleDiscountFixedAmount, saleDiscountPeriods, saleDiscountSeatPriceOverride, planStartMonth, referralCode, referrerName, advertisementId, publisherId, shopperId, promoCode, groupMemberId, idType, and industry<br/>**Note:** saleDiscountPercent, saleDiscountAmount, saleDiscountFixedAmount, saleDiscountPeriods, and saleDiscountSeatPriceOverride are reserved for DoucSign use only.|
|socialAccountInformation|No||A complex type that contains the following information:<br/><ul><li>email – The users email address.</li><li>provider – The social account provider (Facebook, Yahoo, etc.).</li><li>socialId</li><li>userName – The full user name for the account.</li></ul>|

## accountSettings:

The accountSettings set the account feature information.

|Name|Value|Aurthorization Required|Description|
|---------------|------------|-----------------|--------------------------------------------------------|
|allowEnvelopeCorrect|Boolean|Admin|When true, the account allows in process envelopes to be corrected.|
|allowInPerson|Boolean|SysAdmin|When true, the account allows In Person Signing.|
|allowOfflineSigning|Boolean|Admin|When true, the account can use Offline Signing and envelopes signed using offline signing on mobile devices are synchronized with this account. This option and the inSessionEnabled option must both be enabled (true) for a caller to use offline signing.|
|allowExpressSignerCertificate|Boolean|Admin|When true, senders are allowed to use the DocuSign Express digital signatures.|
|allowOpenTrustSignerCertificate|Boolean|Admin|When true, senders are allowed to use the OpenTrust digital signatures.|
|allowSafeBioPharmaSignerCertificate|Boolean|Admin|When true, senders are allowed to use the SAFE BioPharma digital signatures.|
|allowSharedTabs|Boolean|Admin|When true, the account allows users to share custom tags (fields).<br/>Note: This setting is only shown when getting account settings. It cannot be modified.|
|allowSignerReassign|Boolean|Admin|When true, the account allows signers to reassign an envelope.|
|attachCompletedEnvelope|Boolean|SysAdmin|When true, envelope documents are included as a PDF file attachment for signing completed emails.|
|autoNavRule|String|Admin|The auto-navigation rule for the account.<br/>Enumeration values are: Off, RequiredFields, RequiredAndBlankFields, AllFields, PageThenRequiredFields, PageThenRequiredAndBlankFields, PageThenAllFields.|
|canSelfBrandSend|Boolean|SysAdmin|When true, account administrators can self-brand their sending console through the DocuSign Console.|
|canSelfBrandSign|Boolean|SysAdmin|When true, account administrators can self-brand their signing console through the DocuSign Console.|
|disableUploadSignature|Boolean|Admin|When true, signers cannot use the upload signature/initials image option when signing a document.|
enableAutoNav|Boolean|SysAdmin or EnableAutoNavByDSAdmin is set|When true, the auto-navigation is enabled for the account.|
|enableBulkRecipient|Boolean|Admin|When true, the account allows bulk sending of envelopes.|
|enableCalculatedFields|Boolean|Admin & AllowExpression is set|When true, this account can use the Calculated Fields feature.|
|enableDSPro|Boolean|SysAdmin|When true, this account can send and manage envelopes from the DocuSign Desktop Client.|
|enableEnvelopeStampingByAccountAdmin|Boolean|SysAdmin or account has EnableEnvelopeStampingByDSAdmin set|When true, senders for this account can choose to have the envelope ID stamped in the document margins.|
|enablePaymentProcessing|Boolean|Admin & AllowPaymentProcessing is set.|When true, Payment Processing is enabled for the account.|
|enablePowerForm|Boolean|SysAdmin|When true, PowerForm access is enabled for the account.|
|enableRequireSignOnPaper|Boolean|Admin|When true, the account can use the requireSignOnPaper option.|
|enableReservedDomain|Boolean|SysAdmin|When true, an account administrator can reserve web domain and users.|
|enableSendToAgent|Boolean|SysAdmin|When true, this account can use the Agent Recipient Type.|
|enableSendToIntermediary|Boolean|Admin & AllowSendToIntermediary is set|When true, this account can use the Intermediary Recipient Type.|
|enableSendToManage|Boolean|Admin|When true, this account can use the Editor Recipient Type.|
|enableSequentialSigningAPI|Boolean|SysAdmin|When true, the account can define the routing order of recipients for envelopes sent using the DocuSign API.|
|enableSequentialSigningUI|Boolean|SysAdmin|When true, the account can define the routing order of recipients for envelopes sent using the DocuSign console.|
|enableSignerAttachments|Boolean|Admin|When true, a user can request attachments from a signer.|
|enableSignOnPaper|Boolean|Admin|When true, a user can allow signers to use the sign on paper option.|
|enableSignOnPaperOverride|Boolean|Admin|When true, a user can override the default account setting for the sign on paper option.|
|enableTransactionPoint|Boolean|SysAdmin|When true, Transaction Point is enabled for this account.|
|enableVaulting|Boolean|SysAdmin|When true, this account can use electronic vaulting for documents.|
|envelopeIntegrationAllowed|String|SysAdmin|Shows the envelope integration rule for the account.<br/>Enumeration values are: NotAllowed, Full, IntegrationSendOnly.|
|envelopeIntegrationEnabled|Boolean|Admin & EnvelopeIntegrationAllowed is set|When true, envelope integration is enabled for the account.|
|envelopeStamplingDefaultValue|Boolean|(GET only)|When true, envelopes sent by this account automatically have the envelope ID stamped in the margins, unless the sender selects not to have them stamped.|
|iDCheckExpire|String|Admin|Indicates when a user’s authentication expires.<br/>Enumeration values are: Always, Never, Variable. Variable uses the value in IDCheckExpireDays.|
|iDCheckExpireDays|Integer|Admin|The number of days before a user’s authentication expires. This is only active if the IDCheckExpire value is Variable.|
|iDCheckRequired|String|Admin|Indicates if authentication is required by envelope signers.<br/>Enumeration values are: Always, Never, or Optional. Optional means the authentication is determined by the sender.|
|inPersonIDCheckQuestion|String|Admin|The default question used by the In Person signing host for an In Person signing session.|
|inSessionEnabled|Boolean|Admin|When true, the account can use In Session (embedded) and offline signing. This option and the allowOfflineSigning option must both be enabled (true) for a caller to use offline signing.|
|mobileSessionTimeout|String|Admin|Sets the amount of idle activity time, in minutes, before a mobile user is automatically logged off of the system. If the setting is 0, then DocuSign mobile application users are never automatically logged off the system. The minimum setting is 1 minute and the maximum setting is 120 minutes.<br/>Note this setting only applies to the DocuSign for iOS v2.8.2 or later mobile app.|
|phoneAuthRecipientMayProvidePhoneNumber|Boolean|Admin|When true, senders can select to allow the recipient to provide a phone number for the Phone Authentication process.|
|pkiSignDownloadedPDFDocs|String|Admin|The policy for adding a digital certificate to downloaded, printed and emailed documents.<br/>Enumeration values are: NoSign, NoSignAllowUserOverride, YesSign|
|rsaVeridAccountName|String|Admin|The RSA account name.<br/>**Note:** Modifying this value might inadvertently disrupt your ID Check capability. Ensure you have the correct value before changing this|
|rsaVeridPassword|String|Admin|The password used with the RSA account.<br/>**Note:** Modifying this value might inadvertently disrupt your ID Check capability. Ensure you have the correct value before changing this.|
|rsaVeridRuleset|String|Admin|The RSA rule set used with the account.<br/>**Note:** Modifying this value might inadvertently disrupt your ID Check capability. Ensure you have the correct value before changing this.|
|rsaVeridUserId|String|Admnin|The user ID for the RSA account.<br/>**Note:** Modifying this value might inadvertently disrupt your ID Check capability. Ensure you have the correct value before changing this.|
|selfSignedRecipientEmailDocument|String|Admin|This sets the account setting for how self-signed documents are presented to the email recipients. Enumeration values are:<ul><li>include_pdf: With this setting a PDF of the completed document is attached to the email</li><li>include_link: With this setting a secure link to the self-signed documents is included in the email.</li></ul>|
|selfSignedRecipientEmailDocumentUserOverride|Boolean|Admin|When true the selfSignedRecipientEmailDocument userSetting can be set for an individual user. The userSetting will override the account setting.|
|sessionTimeout|Integer|Admin|The amount of idle activity time, in minutes, before a user is automatically logged out of the system. The minimum setting is 20 minutes and the maximum setting is 120 minutes.|
|signDateFormat|String|Admin|The date/time format applied to Date Signed fields for the account.|
|signerAttachCertificateToEnvelopePDF|Boolean|AccountAdmin & account is selected in AccountSigningSettings|When true, the Certificate of Completion is included in the envelope documents PDF when it is downloaded.|
|signerCanCreateAccount|Boolean|AccountAdmin & account is selected in AccountSigningSettings|When true, the signer without a DocuSign account can create a DocuSign account after signing.|
|signerCanSignOnMobile|Boolean|AccountAdmin & account is selected in AccountSigningSettings|When true, signers can use the DocuSign mobile signing user interface.|
|signerInSessionUseEnvelopeCompleteEmail|Boolean|Admin|When true, an envelope complete email is sent to an In Session (embedded) or offline signer after DocuSign processes the envelope.|
|signerMustHaveAccount|Boolean|AccountAdmin & account is selected in AccountSigningSettings|When true, senders can only send an envelope to a recipient that has a DocuSign account.|
|signerMustLoginToSign|Boolean|AccountAdmin & account is selected in AccountSigningSettings|When true, an envelope signer must log in to the DocuSign console to sign an envelope.|
|signerShowSecureFieldInitialValues|Boolean|AccountAdmin & account is selected in AccountSigningSettings|When true, the initial value of all SecureFields is written to the document when sent.|
|useAccountLevelEmail|Boolean|AccountAdmin & account is selected in AccountSigningSettings|When true, the content of notification emails is determined at the account level.|
|usesAPI|Boolean|SysAdmin|When true, the account can use the DocuSign API.|

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/
    
    {
      "accountName":"String content",
      "accountSettings":[{
       "name":"String content",
       "value":"String content"
      }],
    "addressInformation":{
      "address1":"String content",
      "address2":"String content",
      "city":"String content",
      "country":"String content",
      "fax":"String content",
      "phone":"String content",
      "postalCode":"String content",
      "state":"String content"
    },
    "creditCardInformation":{
      "cardNumber":"String content",
      "cardType":"String content",
      "expirationMonth":"String content",
      "expirationYear":"String content",
      "nameOnCard":"String content"
    },
    "distributorCode":"String content",
    "distributorPassword":"String content",
    "initialUser":{
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
    },
    "planInformation":{
    "currencyCode":"String content",
    "planFeatureSets":[{
      "currencyFeatureSetPrices":[{
        "currencyCode":"String content",
        "currencySymbol":"String content",
        "envelopeFee":"String content",
        "fixedFee":"String content",
        "seatFee":"String content"
      }],
      "envelopeFee":"String content",
      "featureSetId":"String content",
      "fixedFee":"String content",
      "isActive":"String content",
      "isEnabled":"String content",
      "name":"String content",
      "seatFee":"String content"
    }],
    "planId":"String content",
    "freeTrialDaysOverride":"String content"
    },
    "referralInformation":{
      "advertisementId":"String content",
      "enableSupport":"String content",
      "groupMemberId":"String content",
      "idType":"String content",
      "includedSeats":"String content",
      "industry":"String content",
      "planStartMonth":"String content",
      "promoCode":"String content",
      "publisherId":"String content",
      "referralCode":"String content",
      "referrerName":"String content",
      "saleDiscountAmount":"String content",
      "saleDiscountFixedAmount":"String content",
      "saleDiscountPercent":"String content",
      "saleDiscountPeriods":"String content",
      "saleDiscountSeatPriceOverride":"String content",
      "shopperId":"String content"
    },
    "socialAccountInformation":{
      "email":"String content",
      "provider":"String content",
      "socialId":"String content",
      "userName":"String content"
      }
    }

## Response
The response returns the new account ID, password and the default user information.

The following example shows the response json body.

### Example Response Body

     {
       "accountId":"String content",
       "apiPassword":"String content",
       "baseUrl":"String content",
       "userId":"String content"
     }
