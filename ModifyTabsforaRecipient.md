# Modify Tabs for a Recipient

This modifies one or more tabs for a recipient to a draft envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients/{recipientId}/tabs

## HTTP Method

    PUT

## Parameters

The parameters used to modify tabs are the same as those used in an envelope,
but you can only modify existing tabs and the tabId must be included.
See the [Tab Types and Parameters](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Tab%20Parameters.htm) section for more information about the tabs.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|tabId|Yes|String|The unique identifier for the tab. The tabid can be retrieved with the [GET call](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Get%20Tab%20Information%20for%20a%20Recipient.htm).|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/
    recipients/{recipientId}/tabs
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "approveTabs":[{
        <Tab information removed>
      }],
      "titleTabs":[{
        <Tab information removed>
      }],
      "signHereTabs":[{
        <Tab information removed>
      }]
    }

## Response

The response returns the success or failure of each tab being modified and the envelope ID.
Failed operations on array elements will add the “errorDetails” structure containing an error
code and message. If “errorDetails” is null, then the operation was successful for that item.
