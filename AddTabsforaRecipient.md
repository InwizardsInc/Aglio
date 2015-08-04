# Add Tabs for a Recipient

This adds one or more tabs for a recipient. If can be used to add tabs to a
draft envelope or to add tabs to an in process envelope.

To add tabs to an in process envelope, the account must have envelope correct enabled,
the envelope status must be “Sent” and the recipient status must be “Created” or “Sent.”
If these conditions are met, the POST opens the envelope in correct mode, adds the tabs
and exits correct mode.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients/{recipientId}/tabs

## HTTP Method

    POST

## Parameters

The parameters used to add tabs are the same as those used in an envelope. See the [Tab Types and Parameters](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Tab%20Parameters.htm) section for more information about the tabs.

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}
    /envelopes/{envelopeId}/recipients/{recipientId}/tabs
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "approveTabs":[{
      Tab information removed>
      }],
      "titleTabs":[{
      Tab information removed>
      }],
      "signHereTabs":[{
      Tab information removed>
      }]
    }

## Response

The response returns the success or failure of each document being added to the envelope
and the envelope ID. Failed operations on array elements will add the “errorDetails” structure
containing an error code and message. If “errorDetails” is null, then the operation was successful for that item.
