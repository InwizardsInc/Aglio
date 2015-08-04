# Get Envelope or Template Lock Information

This returns general information about the envelope lock.

If the call is made by the lockedByUser and the request has the same integrator key as original,
then the X-DocuSign-Edit header and additional lock information is included in the response.
This allows users to recover a lost editing session token and the X-DocuSign-Edit header.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/lock

## HTTP Method

    GET

## Parameters

The only required parameter is the envelope or template ID.

>**Note:** When working with a template, the templateId is used in place of the envelopeId.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/
    {envelopeId}/lock
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    X-DocuSign-Edit = <DocuSignEdit><LockToken>{token from response}
    </LockToken><LockDurationInSeconds>600</LockDurationInSeconds></DocuSignEdit>

## Response

The response returns the lock information. If the call is made by the lockedByUser and the
request has the same integrator key as original, then the X-DocuSign-Edit header and additional
lock information is included in the response. This allows users to recover a lost editing session
token and the X-DocuSign-Edit header.

### Example Response (standard)

    {
      "lockedByUser": {
        "userName": "string",
        "email": "string",
        "userId": "string"
      },
      "lockedByApp": "string",
      "lockedUntilDateTime": "dateTime",
      "lockType": "string"
    }

### Example Response (for lockedByUser)

    X-DocuSign-Edit: {"token": "token_string", "lockDurationInSeconds": "string"}
    
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
