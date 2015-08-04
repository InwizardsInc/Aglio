# Delete Tabs for a Recipient

This deletes one or more tabs associated with a recipient in a draft envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients/{recipientId}/tabs

## HTTP Method

    DELETE

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|tabId|Yes|String|The unique identifier for the tab. The tabid can be retrieved with the [GET call](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Get%20Tab%20Information%20for%20a%20Recipient.htm).|

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/
    envelopes/{envelopeId}/recipients/{recipientId}/tabs
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json
    
    {
      "approveTabs":[{
        "tabId":"String content"
      },
      {
        "tabId":"String content"
      }
      ],
      "titleTabs":[{
        "tabId":"String content"
      }],
      "signHereTabs":[{
        "tabId":"String content"
      }]
    }

## Response

The response returns the success or failure of each document being added to the
envelope and the envelope ID. Failed operations on array elements will add the
“errorDetails” structure containing an error code and message. If “errorDetails”
is null, then the operation was successful for that item.
