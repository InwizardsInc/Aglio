# Post Sender View

This provides a URL to start the sending view of the DocuSign UI. This is a one-time use login token that allows the user to be placed into the DocuSign sending view.

Upon sending completion, the user is returned to the return URL provided by the API application.

>**Important:** iFrames should not be used for embedded operations on mobile devices due to screen space issues. For iOS devices DocuSign recommends using a WebView.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/views/sender

## HTTP Method

    POST

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|returnUrl|Yes|String|Identifies the return point after sending the envelope.<br/>DocuSign returns to the URL and includes an event parameter that can be used to redirect the recipient to another location.<br/>The possible event parameters returned are:<br/><ul><li>send (user sends the envelope)</li><li>save (user saves the envelpe)</li><li>cancel (user cancels the sending transaction. No envelopeId is returned in this case.)</li><li>error (there is an error when performing the send)</li><li>sessionEnd (the sending session ends before the user completes another action)</li></ul>|

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/views/sender
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "returnUrl":"String content"
    }

## Response

The response returns the sender view URL.

The following example shows the response json body.

### Example Response Body

    {
      "url":"String content"
    }
