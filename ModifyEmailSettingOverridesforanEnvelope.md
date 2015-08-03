# Modify Email Setting Overrides for an Envelope

This modifies existing email override settings for the envelope. 
Note that modifying email settings will only affect email communications 
that occur after the modification was made.

This can also be used to delete an individual
email override setting by using an empty string for the value to be deleted.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/email_settings

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|replyEmailAddressOverride|No|String|The Reply To email used for the envelope. DocuSign will verify a correct email format is used, but does not verify that the email is active. This can be a maximum of 100 characters.|
|replyEmailNameOverride|No|String|The name associated with the Reply To email address. This can be a maximum of 100 characters.|
|bccEmailAddresses|No|Array of strings|Only users with canManageAccount setting can use this option.<br/>This is an array of up to 5 email addresses the envelope is sent to as a BCC email.<br/>bccEmailAddressId – This is the DocuSign generated identification for the BCC email address. It is required to change the BCC email address. It can be determined using the [GET](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Get%20Email%20Setting%20Overrides%20for%20an%20Envelope.htm).<br/>email – The BCC email address. DocuSign verifies that the email format is correct, but does not verify that the email is active. This can be a maximum of 100 characters. Using this overrides the BCC for Email Archive information setting for this envelope.<br/><br/>Example: if your account has BCC for Email Archive set up for the email address ‘archive@mycompany.com’ and you send an envelope using the BCC Email Override to send a BCC email to ‘salesarchive@mycompany.com’, then a copy of the envelope is only sent to the ‘salesarchive@mycompany.com’ email address.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/email_settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "replyEmailAddressOverride": "string",
      "replyEmailNameOverride": "string",
      "bccEmailAddresses": [
        {
          "bccEmailAddressId": "string",
          "email": "string"
        },
        {
          "bccEmailAddressId": "string",
          "email": "string"
        }
      ]
    }

## Response

The response returns a success or failure and the email settings information for the envelope.

The following example shows the response json body.

### Example Response Body

    {
      "replyEmailAddressOverride": "string",
      "replyEmailNameOverride": "string",
      "bccEmailAddresses": [
        {
        "bccEmailAddressId": "string",
        "email": "string"
        },
        {
          "bccEmailAddressId": "string",
          "email": "string"
        }
      ]
    }
