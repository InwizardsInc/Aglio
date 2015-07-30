# Get a Connect Configuration Information

This allows you to retrieve the information about one DocuSign Connect configuration.

>**Note:** Connect must be enabled for your account to use this function.

## URL

    /accounts/{accountId}/connect/{connectId}

## HTTP Method

   GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect/{connectId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the information for the selected Connect configuration.

The following example shows the response json body.

## Example Response Body

    {
      "allUsers":"String content",
      "allowEnvelopePublish":"String content",
      "connectId":"String content",
      "enableLog":"String content",
      "envelopeEvents":"String content",
      "includeCertSoapHeader":"String content",
      "includeDocuments":"String content",
      "includeSenderAccountasCustomField":"String content",
      "includeTimeZoneInformation":"String content",
      "name":"String content",
      "recipientEvents":"String content",
      "requiresAcknowledgement":"String content",
      "signMessageWithX509Certificate":"String content",
      "soapNamespace":"String content",
      "urlToPublishTo":"String content",
      "useSoapInterface":"String content",
      "userIds":"String content",
      "includeDocumentFields": "boolean"
    }
