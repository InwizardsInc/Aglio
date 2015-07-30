# Get Connect Configuration Information

This allows you to retrieve all the DocuSign Custom Connect definitions for your account.

>**Note:** Connect must be enabled for your account to use this function.
> This does not retrieve information for Connect configurations for Box, eOriginal or Salesforce.

## URL

    /accounts/{accountId}/connect

## HTTP Method

    GET

## Parameters

No parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>
                               {integrator_key}</IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the information for all the Connect configurations for the account and a count of the total number of configurations.

The following example shows the response json body.

### Example Response Body

    {
      "configurations":[{
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
      },
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
        "userIds":"String content"}],
        "includeDocumentFields": "boolean"
     }],
      "totalRecords":"String content"
    }
