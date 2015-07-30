# Get Disclosure

This returns the Electronic Record and Signature Disclosure, with html formatting, associated with the account.
You can use an optional query string to set the language for the disclosure.

## URL

    /accounts/{accountId}/consumer_disclosure
    Optional query addition: langCode={value}

## HTTP Method

    GET

## Parameters

There are no required parameters,
but the following optional query can be added to set the language of the disclosure in the response.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|langCode|No|String|The simple type enumeration the language used in the response. The supported languages, with the language value shown in parenthesis, are:Arabic (ar), Bulgarian (bg), Czech (cs), Chinese Simplified (zh_CN), Chinese Traditional (zh_TW), Croatian (hr), Danish (da), Dutch (nl), English US (en), English UK (en_GB), Estonian (et), Farsi (fa), Finnish (fi), French (fr), French Canada (fr_CA), German (de), Greek (el), Hebrew (he), Hindi (hi), Hungarian (hu), Bahasa Indonesia (id), Italian (it), Japanese (ja), Korean (ko), Latvian (lv), Lithuanian (lt), Bahasa Melayu (ms), Norwegian (no), Polish (pl), Portuguese (pt), Portuguese Brazil (pt_BR), Romanian (ro), Russian (ru), Serbian (sr), Slovak (sk), Slovenian (sl), Spanish (es),Spanish Latin America (es_MX), Swedish (sv), Thai (th), Turkish (tr), Ukrainian (uk) and Vietnamese (vi).<br/>Additionally, the value can be set to ‘browser’ to automatically detect the browser language being used by the viewer and display the disclosure in that language|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/consumer_disclosure
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>{password}
                               </Password><IntegratorKey>{integrator_key}</IntegratorKey>
                               </DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the accountEsignId with the GUID and the esignAgreement with the Electronic Record and Signature Disclosure text.
The disclosure text includes the html formatting.

The following example shows the response json body.
For brevity, the example only shows a portion of the Electronic Record and Signature Disclosure text.

## Request

### Example Request Body

    {
      "accountEsignId": "string",
      "esignAgreement": "\r\n<B>CONSUMER DISCLOSURE</B>\r\n<P></P>\r\nFrom time to time,
      Rest Tester Account (we, us or Company) may be required by law to provide to you
      certain written notices or disclosures. Described below are the terms and conditions
      for providing to you such notices and disclosures electronically through the
      DocuSign, Inc. (DocuSign) electronic signing system. Please read the information
      below carefully and thoroughly, and if you can access this information electronically
      to your satisfaction and agree to these terms and conditions, please confirm your
      agreement by clicking the “I agree” button at the bottom of this document.\r\n<P></P>"
    }
