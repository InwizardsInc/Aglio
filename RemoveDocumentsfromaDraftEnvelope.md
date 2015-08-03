# Remove Documents from a Draft Envelope

This removes one or more document from an existing draft envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents

## HTTP Method

    DELETE

## Parameters

See [Document parameters](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Document%20Parameters.htm)

## Response

### example Response Body

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
