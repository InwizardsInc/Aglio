# Add Email Setting Overrides to an Envelope

This adds email override settings, changing the reply to email address or name
or the BCC for email archive information, for the envelope. Note that adding email
settings will only affect email communications that occur after the addition was made.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/email_settings

## HTTP Method

    POST

## Parameters

    POST

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|replyEmailAddressOverride|No|String|The Reply To email used for the envelope. DocuSign will verify a correct email format is used, but does not verify that the email is active. This can be a maximum of 100 characters.|
|replyEmailNameOverride|No|String|The name associated with the Reply To email address. This can be a maximum of 100 characters.|
|bccEmailAddresses|No|Array of strings|Only users with canManageAccount setting can use this option.<br/>This is an array of up to 5 email addresses the envelope is sent to as a BCC email.<br/>email – The BCC email address. DocuSign verifies that the email format is correct, but does not verify that the email is active. This can be a maximum of 100 characters. Using this overrides the BCC for Email Archive information setting for this envelope.<br/><br/>Example: if your account has BCC for Email Archive set up for the email address ‘archive@mycompany.com’ and you send an envelope using the BCC Email Override to send a BCC email to ‘salesarchive@mycompany.com’, then a copy of the envelope is only sent to the ‘salesarchive@mycompany.com’ email address.|

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}
    /envelopes/{envelopeId}/email_settings
    
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
          "email": "string"
        },
        {
          "email": "string"
        }
      ]
    }
  
  ## Response
  
The response returns a success or failure and the information added to the envelope and the bccEmailAddressId associated with the bccEmailAddresses.

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
