# Get Envelope Recipient Status

This returns the status for all recipients of a single envelope and identifies the
current routing order. The current routing order is a number that matches up to the
routingOrder for envelope recipients, which shows that the envelope has been sent to
a recipient, but the recipient has not completed their actions.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients
    Optional query strings: include_tabs={true or false}, include_extended={true or false}

## HTTP Method

    GET

## Parameters

The only required parameter is the envelope ID. If the optional query include_tabs
is set to true, the tabs associated with the recipient are returned. If the optional
query include_extended is set to true, the extended properties are returned.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/recipients
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the recipient types and current routing order.
The recipient types includes the recipient name, email, ID, recipient type,
routing order, tab information, delivery method, authentication status
(including the date/time and result of the authentication) status
(including the date/time of the status changes) and, if the recipient status
is declined and a reason is required, a decline reason added by the recipient.
Additionally, the tab information for Company, Date, Email, Number, SSN, Text, Title,
and Zip tabs includes the original value (originalValue) of the tab when it was sent to the recipient.

The following example shows the response json body.

### Example Response Body

    {
      "agents":[]
      "carbonCopies":[],
      "certifiedDeliveries":[],
      "currentRoutingOrder":"String content",
      "editors":[],
      "inPersonSigners":[],
      "intermediaries":[],
      "recipientCount":"String content",
      "signers":[{
        "deliveredDateTime": "String content",
        "recipientAuthenticationStatus":{
        "(authentication status result)":
        "eventTimestamp":"String content"
        "status":"String content"
        }
      },
      "recipientId": "String content",
      "requireIdLookup": "String content",
      "roleName":"String content",
      "routingOrder": "String content",
      "signedDateTime": "String content",
      "status": "String content",
      "email": "String content",
      "name": "String content",
      "deliveryMethod": "String content"
      }]
    }
