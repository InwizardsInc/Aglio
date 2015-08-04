# Get Tab Information for a Recipient

This retrieves information about the tabs associated with a recipient in a draft envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients/{recipientId}/tabs

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Response

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/
    envelopes/{envelopeId}/recipients/{recipientId}/tabs
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of tabs associated with the recipient..
The tab information includes a tabId that can be used when deleting a tab.
Additionally for Company, Date, Email, Number, SSN, Text, Title, and Zip tabs 
the response includes the original value (originalValue) of the tab when it was sent
to the recipient. The following example shows the response json body.

### Example Response Body

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
