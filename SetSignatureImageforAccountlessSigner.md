# Set Signature Image for Accountless Signer

This sets the signature image for an accountless signer. The supported image
formats for this file are: gif, png, jpeg, and bmp. The file size must be less than 200K.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients/{recipientId}/signature_image

>**Note:**  For the Authentication/Authorization for this call, the credentials must match
> the sender of the envelope, the recipient must be an accountless signer or in person signer,
> the Account has CanSendEnvelope enabled and the SendingUser does not have ExpressSendOnly enabled.

## HTTP Method

    PUT

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/
    {envelopeId}/recipients/{recipientId}/signature_image
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    
    Content-Type: image/gif
    
    <image removed>

## Response

    The response returns a success or failure.
