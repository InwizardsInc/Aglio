# Get One API Request Logging Log File

This returns information for a single log entry.

## URL

    /diagnostics/request_logs/{requestLogId}

## HTTP Method

    GET

## Parameters

No additional parameters are required. The requestLogfId can be retrieved by getting the list of log entries. The Content-Transfer-Encoding header can be set to base64 to retrieve the API request/response as base 64 string. Otherwise the bytes of the request/response are returned.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/diagnostics/request_logs/{requestLogId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    Content-Transfer-Encoding: base64

## Response

    The response returns the bytes of the request/response. 
    If the Content-Transfer-Encoding header was set to base64,
    the log is returned as base 64 string.
