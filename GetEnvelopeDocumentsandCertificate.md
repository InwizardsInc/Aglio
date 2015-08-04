# Get Envelope Documents and Certificate

This retrieves a PDF containing the combined content of all documents and the certificate.
If the account has the Highlight Data Changes feature enabled, there is an option to request
that any changes in the envelope be highlighted.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents/combined
    Optional additions: certificate={true or false}, encrypted={true or false},
    include_metadata={true or false}, language={string}, show_changes={true}, watermark={true or false}

## HTTP Method

    GET

## Parameters

The only required parameter is the envelope ID, but the following optional parameters can be added to change the results.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|certificate|No|Boolean|This option can remove the envelope signing certificate from the download.|
|encrypted|No|Boolean|When true the PDF bytes returned in the response are encrypted for all the key managers configured on your DocuSign account. The documents can be decrypted with the KeyManager Decrypt Document API.|
|include_metadata|No|Boolean|When false, metadata that could invalidate a digital signature in the PDF is excluded from the response.|
|language|No|String|Sets the language for the Certificate of Completion in the response. The supported languages, with the language value shown in parenthesis, are: Chinese Simplified (zh_CN), , Chinese Traditional (zh_TW), Dutch (nl), English US (en), French (fr), German (de), Italian (it), Japanese (ja), Korean (ko), Portuguese (pt), Portuguese (Brazil) (pt_BR), Russian (ru), Spanish (es).|
|show_changes|No|Boolean|Optional. When set to true, any changed fields for the returned PDF are highlighted in yellow and optional signatures or initials outlined in red.|
|watermark|No|Boolean|If the account has the watermark feature enabled and the envelope is not complete, the watermark for the account is added to the PDF documents. This option can remove the watermark.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/documents/combined
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns all the PDFs in an envelope and a PDF version of the envelope certificate as a byte stream. If show_changes was included, any changed fields are highlighted in the PDF.
