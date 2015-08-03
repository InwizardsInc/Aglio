# Add Document

This adds another document to an existing draft envelop.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents/{documentId}

## HTTP Method

    PUT

## Parameters

See [Document parameters](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Document%20Parameters.htm)

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/
                      envelopes/{envelopeId}/documents/{documentId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Content-Type: application/pdf
    Content-Disposition: file; filename="test1.pdf"; documentid=1; fileExtension="pdf"
    
    <Bytes of PDF omitted>

## Response

    The response only returns a success or failure.
