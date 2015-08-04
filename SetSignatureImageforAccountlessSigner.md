# Set Signature Image for Accountless Signer

This returns the structure of a single signature with a known signature name.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients/{recipientId}/signature

>**Note:** For the Authentication/Authorization for this call, the credentials
> must match the sender of the envelope, the recipient must be an accountless signer
> or in person signer, the Account has CanSendEnvelope enabled and the SendingUser
> does not have ExpressSendOnly enabled.

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/
    {envelopeId}/recipients/{recipientId}/signature
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>

## Response

The response returns information for the request recipient signature. The following example shows the response json body.

### Example Response Body

    {
      "adoptedDateTime":"String content",
      "createdDateTime":"String content",
      "initials150ImageId":"String content",
      "initialsImageUri":"String content",
      "signature150ImageId":"String content",
      "signatureFont":"String content",
      "signatureId":"String content",
      "signatureImageUri":"String content",
      "signatureInitials":"String content",
      "signatureName":"String content",
      "signatureType":"String content"
    }
