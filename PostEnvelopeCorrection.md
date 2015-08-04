# Post Envelope Correction

This provides a URL to start the correction view of the DocuSign UI.

>**Important:**  iFrames should not be used for embedded operations on mobile devices
> due to screen space issues. For iOS devices DocuSign recommends using a WebView.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/views/correct

## HTTP Method

    POST

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|returnUrl|Yes|String|Identifies the return point after correcting the envelope.<br/>DocuSign returns to the URL and includes an event parameter that can be used to redirect the recipient to another location.<br/>The possible event parameters returned are:<br/><ul><li>send (user corrects and sends the envelope)</li><li>save (user saves the envelpe)</li><li>cancel (user cancels the transaction.)</li><li>error (there is an error when performing the correct or send)</li><li>sessionEnd (the session ends before the user completes another action)</li></ul>|
|suppressNavigation|No|String|Sets whether the window is displayed with or without dressing.|

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/views/correct
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>{password}
                               </Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "returnUrl":"String content",
      "suppressNavigation":"String content"
    }

## Response

The response returns the correction view url.

The following example shows the response json body.

### Example Response Body

    {
      "url":"String content"
    }
