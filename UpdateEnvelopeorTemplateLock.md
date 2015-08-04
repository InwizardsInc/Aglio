# Update Envelope or Template Lock

This is used to extend the lock duration time or update the lockedByApp information.
The user and integrator key must match the lockByUser user and integrator key information
and the X-DocuSign-Edit header must be included or an error will be generated.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/lock

## HTTP Method

    PUT

## Parameters

The only required parameter is the envelope or template ID.

>**Note:** When working with a template, the templateId is used in place of the envelopeId.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|lockDurationInSeconds|No|strung|Optional setting to set the time, in seconds, until the lock expires when there is no activity on the envelope.<br/>If no value is entered, then the default value of 300 seconds is used. The maximum value is 1,800 seconds.<br/>The lock duration can be extended.|
|lockedByApp|No|String|Optional setting that provides an easily understood name of the application that is locking the envelope.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/
    {envelopeId}/lock
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    X-DocuSign-Edit = <DocuSignEdit><LockToken>{token from response}
    </LockToken><LockDurationInSeconds>600</LockDurationInSeconds></DocuSignEdit>
    {
      "lockDurationInSeconds": "string",
      "lockedbyApp": "string"
    }

## Response

The response returns the same information as locking the envelope or template.

The following example shows the response json body.

### Example Response Body

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
