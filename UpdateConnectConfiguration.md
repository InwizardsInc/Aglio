# Update a Connect Configuration

This allows you to update a DocuSign Connect configuration for your account.

>**Note:** Connect must be enabled for your account to use this function.
> This cannot be used to update Connect configurations for Box, eOriginal or Salesforce.

## URL

    /accounts/{accountId}/connect

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|allUsers|No|Boolean|When true, the tracked envelope and recipient events for all users, including users that are added a later time, are sent through Connect.|
|allowEnvelopePublish|No|Boolean|When true, data is sent to the urlToPublishTo web address. This option can be set to false to stop sending data while maintaining the Connect configuration information.|
|connectId|Yes|Integer|The DocuSign generated ID for the Connect configuration.|
|enableLog|No|Boolean|This turns Connect logging on or off. When true, logging is turned on.|
|envelopeEvents|No|String|A comma separated list of “Envelope” related events that are tracked through Connect.<br/>The possible event values are: Sent, Delivered, Completed, Declined, and Voided.|
|includeDocuments|No|Boolean|When true, Connect will send the PDF document along with the update XML.|
|includeDocumentFields|No|Boolean|When true, the Document Fields associated with envelope documents are included in the data. Document Fields are optional custom name-value pairs added to documents using the API.|
|includeEnvelopeVoidReason|No|Boolean|When true, Connect will include the voidedReason for voided envelopes.|
|includeSenderAccount|No|Boolean|When true, Connect will include the sender account as Custom Field in the data.|
|includeTimeZoneInformation|No|Boolean|When true, Connect will include the envelope time zone information.|
|name|No|String|The name of the Connect configuration. The name helps identify the configuration in the list.|
|recipientEvents|No|String|A comma separated list of “Recipient” related events that are tracked through Connect.<br/><br/>The possible event values are: Sent, Delivered, Completed, Declined, AuthenticationFailed, and AutoResponded.|
|requireAcknowledgement|No|Boolean|When true and a publication message fails to be acknowledged, the message goes back into the queue and the system will retry delivery after a successful acknowledgement is received. If the delivery fails a second time, the message is not returned to the queue for sending until Connect receives a successful acknowledgement and it has been at least 24 hours since the previous retry. There is a maximum of ten retries<br/><br/>Alternately, you can use Republish Connect Information to manually republish the envelope information.|
|signMessageWithCertificate|No|Boolean|When true, Connect messages are signed with an X509 certificate. This provides support for 2-way SSL.|
|soapNameSpace|No*|String|The namespace of the SOAP interface.<br/><br/>* This is required if useSoapInterface is set to true.|
|urlToPublishTo|Yes|String|This is the web address and name of your listener or Retrieving Service endpoint. You need to include HTTPS:// in the web address.|
|useSoapInterface|No|Boolean|Set to true if the urlToPublishTo is a SOAP endpoint.|
|userIds|No*|String|A comma separated list of userIds. This sets the users associated with the tracked envelope and recipient events. When one of the event occurs for a set user, the information is sent through Connect.<br/><br/>* If allUsers is set to ‘false’ then you must provide a list of user id’s.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>
                              {integrator_key}</IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "allUsers": "boolean",
      "allowEnvelopePublish": "boolean",
      "connectId":"String content",
      "enableLog": "boolean",
      "envelopeEvents": "string content",
      "includeDocuments": "boolean",
      "includeEnvelopeVoidReason": "boolean",
      "includeSenderAccountasCustomField": "boolean",
      "includeTimeZoneInformation": "boolean",
      "name": "string content",
      "recipientEvents": "string content",
      "requiresAcknowledgement": "boolean",
      "signMessageWithX509Certificate": "boolean",
      "soapNamespace": "string content",
      "urlToPublishTo": "string content",
      "useSoapInterface": "boolean",
      "userIds": "string content",
      "includeDocumentFields": "boolean"
    }

## Response

The response returns a success or failure with the updated Connect configuration information.

The following example shows the response json body.

### Example Response Body

    {
      "allUsers": "boolean",
      "allowEnvelopePublish": "boolean",
      "connectId":"String content",
      "enableLog": "boolean",
      "envelopeEvents": "string content",
      "includeDocuments": "boolean",
      "includeEnvelopeVoidReason": "boolean",
      "includeSenderAccountasCustomField": "boolean",
      "includeTimeZoneInformation": "boolean",
      "name": "string content",
      "recipientEvents": "string content",
      "requiresAcknowledgement": "boolean",
      "signMessageWithX509Certificate": "boolean",
      "soapNamespace": "string content",
      "urlToPublishTo": "string content",
      "useSoapInterface": "boolean",
      "userIds": "string content",
      "includeDocumentFields": "boolean"
    }
