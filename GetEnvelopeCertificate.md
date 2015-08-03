# Get Envelope Certificate

This retrieves a PDF document containing the certificate for the envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents/certificate
    Optional additions: language={string},

## HTTP Method

    GET

## Parameters

The only required parameter is the envelope ID. The following optional query string can be added to the request.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|language|No|String|Sets the language for the Certificate of Completion in the response. The supported languages, with the language value shown in parenthesis, are: Chinese Simplified (zh_CN), , Chinese Traditional (zh_TW), Dutch (nl), English US (en), French (fr), German (de), Italian (it), Japanese (ja), Korean (ko), Portuguese (pt), Portuguese (Brazil) (pt_BR), Russian (ru), Spanish (es).|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}
    /envelopes/{envelopeId}/documents/certificate
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

    The response returns a PDF version of the envelope certificate as a byte stream.
