# Delete Email Setting Overrides for an Envelope

This deletes all existing email override settings for the envelope.
If you want to delete an individual email override setting, use the PUT
and set the value to an empty string. Note that deleting email settings will
only affect email communications that occur after the deletion and the normal
account email settings are used for future email communications.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/email_settings

## HTTP Method

    DELETE

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/email_settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

    The response returns a success or failure and any error messages associated with a failure.
