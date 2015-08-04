# Delete Envelope or Template Lock

This removes the lock from the envelope or template. The X-DocuSign-Edit header must be included in the request.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/lock
    Optional addition: resend_envelope={true or false}

## HTTP Method

    DELETE

## Parameters

The only required parameter is the envelope or template ID, the following optional query string can be added to the request.

>**Note:** When working with a template, the templateId is used in place of the envelopeId.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|resend_envelope|No|Boolean|Optional setting, when true the envelope is sent to all recipients in the current routing order|

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/
    {envelopeId}/lock?resend_envelope=true
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    X-DocuSign-Edit = <DocuSignEdit><LockToken>{token from response}
    </LockToken><LockDurationInSeconds>600</LockDurationInSeconds></DocuSignEdit>

## Response

    The response returns a success or failure.
