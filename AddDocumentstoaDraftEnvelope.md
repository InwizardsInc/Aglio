# Add Documents to a Draft Envelope

This can be used to add one or more documents to an existing draft envelope
or change the order of documents in a draft envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents

## HTTP Method

    PUT

## Parameters

See [Document parameters](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Document%20Parameters.htm)

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/documents
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    
    Content-Type: multipart/form-data; boundary=AAA
    
    --AAA
    Content-Type: application/json
    Content-Disposition: form-data
    {
      "documents": [{
        "documentId": "String content",
        "name": "String content",
        "order": "String content"
       },
    {
      "documentId": "String content",
      "name": "String content",
      "order": "String content"
      }]
    }
    --AAA
    Content-Type: application/pdf
    Content-Disposition: file; filename="String content"; documentId=10
    
    --AAA
    Content-Type: application/pdf
    Content-Disposition: file; filename=" String content"; documentId=40
    
    --AAA--
    
## Response
    
The response returns the success or failure of each document being added to the envelope and the envelope ID. Failed operations on array elements will add the “errorDetails” structure containing an error code and message. If “errorDetails” is null, then the operation was successful for that item.
