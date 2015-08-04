# Delete Recipients from an Envelope

This is used to delete one or more recipients from a draft or sent envelope.
Recipients to be deleted are listed in the request, with the recipientId being
used as the key for deleting recipients.

If the envelope is “In Process” (has been sent and is not completed or voided),
recipients that have completed their actions cannot be deleted.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients

## HTTP Method

    DELETE

## Parameters

The only required parameter is recipientId.

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/recipients
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
      "signers":[{
        "recipientId":"String content",
      }
    }]
    }

## Response

The response returns if the API execution is successful (200 – OK) or failed.
The response contains a recipient structure similar to that input. If an error
occurred during the DELETE operation for any of the recipients, that recipient will
contain an error node with an errorCode and message.

The following example shows the response json body.

### Example Response Body

    {
      "agents":[{
      }]
      "carbonCopies":[{
      }]
      "certifiedDeliveries":[{
      }]
      "editors":[{
      }]
      "agents":[{
      }]
      "inPersonSigners":[{
      }]
      "intermediaries":[{
      }]
      "signers":[{
        "recipientId":"String content",
        "routingOrder":"String content",
        "status":"Deleted",
        "email":"String content",
        "name":"String content"
      }]
    }
