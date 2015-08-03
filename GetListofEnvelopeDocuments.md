# Get List of Envelope Documents

This returns a list of documents associated with the specified envelope.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents

## HTTP Method

    GET

## Parameters

The only required parameter is the envelope ID.

## Response

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/documents
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of the documents in the selected envelope, with the document ID,
name, type, uri, order, pages, and if the document contains PDF form fields (this is a true/false).

>**Note:** The containPdfFormFields information is only returned for documents that are added
> to an envelope after the initial envelope creation that have not yet been converted.

The following example shows the response json body.

### Example Response Body

    {
      "envelopeId":"String content",
      "envelopeDocuments":[
      {
      "documentId":"String content",
      "name":"String content",
      "type":"String content",
      "uri":"String content",
      "order":"String content",
      "pages":"String content",
      "containPdfFormFields":"String content"
      },
      {
        "documentId":"String content",
        "name":"String content",
        "type":"String content",
        "uri":"String content",
        "order":"String content",
        "pages":"String content",
        "containPdfFormFields":"String content"
      },
     ],
    }
