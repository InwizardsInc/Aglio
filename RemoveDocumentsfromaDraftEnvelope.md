# Remove Documents from a Draft Envelope

This removes one or more document from an existing draft envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents

## HTTP Method

    DELETE

## Parameters

See [Document parameters](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Document%20Parameters.htm)

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}
                                   /envelopes/{envelopeId}/documents
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
     Accept: application/json
    
    Content-Type: application/json
    
    {
      "documents": [{
        "documentId": "String content",
      },
      {
        "documentId": "String content",
      }]
    }
    
## Response
    
The response returns the success or failure of each document being added to the envelope and the envelope ID. Failed operations on array elements will add the “errorDetails” structure containing an error code and message. If “errorDetails” is null, then the operation was successful for that item.
