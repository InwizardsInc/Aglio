# Get List of Unsupported File Types

Retrieves a list of file types (mime-types and file-extensions) that are not supported for upload through the DocuSign system.

## URL

    /accounts/{accountId}/unsupported_file_types

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/unsupported_file_types
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of the file extensions and mime types that are not supported.

The following example shows the response json body.

### Example Response Body

    {
      "fileTypes":[
        {
          "fileExtension":"String content",
          "mimeType":"String content"
        },
        {
          "fileExtension":"String content",
          "mimeType":"String content"
         }
      ]
    }
