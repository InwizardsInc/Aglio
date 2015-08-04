# Post Recipient View

This provides a URL to start the recipient view of the DocuSign UI for a sent envelope. This call cannot be used to view draft envelopes, since those envelopes have not been sent.

>**Important:** iFrames should not be used for embedded operations on mobile devices due to screen space issues. For iOS devices DocuSign recommends using a WebView.

An entry is added into the Security Level section of the DocuSign Certificate of Completion that reflects the “securityDomain” – “authenticationMethod” used to verify the user identity.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/views/recipient

## HTTP Method

    POST

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|clientUserId|Yes|String|A sender created value that shows the recipient is embedded (captive). This can be a maximum of 100 characters.|
|authenticationMethod|Yes|String|A sender created value that indicates the convention used to authenticate the signer. This information is included in the Certificate of Completion.|
|assertionId|No|String|A unique identifier of the authentication event executed by the client application.|
|authenticationInstant|Yes|DateTime|A sender generation value that indicates the date/time that the signer was authenticated.|
|securityDomain|No|String|The domain to which the user authenticated.|
|email|Yes*|String|Specifies the email of the recipient.<br/>* You can use either email and userName or userId to identify the recipient.|
|pingUrl|No|String|The client Url pinged by the DocuSign Signing experience to indicate to the client that Signing is active. An HTTP GET is executed against the client. Note that the response from the client is ignored by DocuSign.<br/>The intent of the ping is for the client to reset the session timer when the request is received.|
|pingFrequency|No|String|This is the interval, in seconds, between pings to the pingUrl.<br/>This is only used if a pingUrl is specified.<br/>This can be 60 to 12000. If no value is specified, a default value of 300 is used.|
|returnUrl|Yes|String|The URL the recipient is directed to on certain events. DocuSign sends returns to the URL and includes an event parameter that can be used to redirect the recipient to another location.<br/>The possible event parameters returned are:<br/><ul><li>cancel (recipient cancels signing)</li><li>decline (recipient declines signing)</li><li>exception (exception occurs)</li><li>fax_pending (recipient has fax pending)</li><li>id_check_faild (recipient failed an ID check)</li><li>session_timeout (session times out)</li><li>signing_complete (recipient completes signing)</li><li>ttl_expired (the TTL expires)</li><li>viewing_complete (recipient completes viewing the envelope)</li></ul>|
|userId|Yes*|String|Specifies the user ID of the recipient.<br/>* You can use with userId or email and userName to identify the recipient. If userId is used and a clientUserId is provided, the userId must match a recipientId (which can be retrieved with a GET recipients call) for the envelope. If userId is used and a clientUserId is not provided, the userId match the userId of the authenticating user.|
|userName|Yes*|String|Specifies the username of the recipient<br/>* You can use either email and userName or userId to identify the recipient.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/views/recipient
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "clientUserId":"String content",
      "authenticationMethod": "String content",
      "assertionId": "String content",
      "authenticationInstant": "String content",
      "securityDomain": "String content"
      "email":"String content",
      "recipientId": "String content",
      "pingUrl": "String content",
      "pingFrequency": "String content",
      "returnUrl":"String content",
      "userId":"String content",
      "userName":"String content"
    }

## Response

The response returns the recipient view url.

The following example shows the response json body.

### Example Response Body

    {
      "url":"String content"
    }

### Setting Default Signing Language for Embedded Signing

When using embedded signing functionality, you can set the language initially loaded for the embedded signing experience.

This is done by appending a locale parameter (&locale={languageCode}) to the URL provided in the response to a POST recipient view request before loading it in your iframe or web control/view.

Note that even when add the locale parameter there is still an order of precedence for determining the language used in the signing experience:<br/>

<ul>
<li>If the sender specifies a language for the recipient when the envelope is sent, that language is used.</li>
<li>If the signing integrator specifies a language in the url locale parameter, that language is used.</li>
<li>If the signer has a DocuSign account, the user language preference is used.</li>
<li>For returning signers, the preference saved from a previous signing is used.</li>
<li>If none of the above conditions are met, the selected browser language is used.</li>
</ul>

Examples: If the response to a POST recipient view request is:

    {
      "url": "https://demo.docusign.net/signing/startinsession.aspx?t=d1cf42f2-30b6-499b-ab54-058fbf438103"
    }

Then first example would open the signing experience in French, the second would use French (Canada), and the third would use Portuguese (Brazil).

    https://demo.docusign.net/signing/startinsession.aspx?t=d1cf42f2-30b6-499b-ab54-058fbf438103&locale=fr

    https://demo.docusign.net/signing/startinsession.aspx?t=d1cf42f2-30b6-499b-ab54-058fbf438103&locale=fr_CA

    https://demo.docusign.net/signing/startinsession.aspx?t=d1cf42f2-30b6-499b-ab54-058fbf438103&locale=pt_BR
