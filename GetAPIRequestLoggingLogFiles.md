# Get API Request Logging Log Files

This returns a list of log entries or to download a zip file of the logs.

## URL

    /diagnostics/request_logs

## HTTP Method

    GET

## Parameters

No additional parameters are required. If the Accept header is set to application/zip, the response will be a zip file containing individual text files, each representing an API request.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/diagnostics/request_logs
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

If the Accept header is set to application/zip, the response will be a zip file containing individual text files, each representing an API request.

If the Accept header is set to application/json or application/xml, the response returns list of log entries in either json or XML. An example json response body is shown below.

## Example Response Body

    {
      "apiRequestLogs": [
        {
          "status": "OK",
          "description": "GetAccountInformation",
          "createdDateTime": "2014-06-03T04:19:01.4200000Z",
          "requestLogId": "90eb155a-9871-4fae-92dd-3aafcfff1d0f"
        },
        {
          "status": "OK",
          "description": "GetAccountInformation",
          "createdDateTime": "2014-06-03T04:19:01.1830000Z",
          "requestLogId": "6762c5fc-c476-4873-8a90-978729ae3b4f"
        }
      ]
    }
