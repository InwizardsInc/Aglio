# Lock an Envelope or Template

This locks the envelope or template, and sets the time until the lock expires,
to prevent other users or recipients from accessing and changing the envelope or template.

>**Note:** Users must have envelope locking capability enabled to use this
> function (userSetting ‘canLockEnvelopes’ must be true for the user).

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/lock

## HTTP Method

    POST

## Parameters

>**Note:** When locking a template, the templateId is used in place of the envelopeId.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|lockDurationInSeconds|No|String|Optional setting to set the time, in seconds, until the lock expires when there is no activity on the envelope.<br/>If no value is entered, then the default value of 300 seconds is used. The maximum value is 1,800 seconds.<br/>The lock duration can be extended.|
|lockType|Yes|String|The type of lock being set.<br/>The accepted value is: edit|
|useScratchPad|No|Boolean|Reserved for future use.<br/>Optional setting that shows if a scratchpad is used for editing information.|
|lockedByApp|No|String|Optional setting that provides an easily understood name of the application that is locking the envelope.|

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/
    {envelopeId}/lock
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      “lockDurationInSeconds”: “string”,
      “lockType”: “string”,
      “useScratchPad”: “boolean”,
      “lockedbyApp”: “string”
    }

## Response

The response returns the lock information and a lock token that is used to in the
X-DocuSign-Edit header to access and make changes to the locked envelope.

    {
      "lockedByUser": {
        "userName": "string",
        "email": "string",
        "userId": "string"
      },
      "lockedByApp": "string",
      "lockedUntilDateTime": "dateTime",
      "lockDurationInSeconds": "string",
      "lockType": "string",
      "useScratchPad": "boolean",
      "token": "string"
    }

The X-DocuSign-Edit header must be included in all subsequent envelope or template calls
to show the user is the owner of the envelope lock. The header structure is:

    X-DocuSign-Edit = <DocuSignEdit><LockToken>{token from response}</LockToken>
    <LockDurationInSeconds>600</LockDurationInSeconds></DocuSignEdit>
