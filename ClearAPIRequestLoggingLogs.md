# Clear API Request Logging Logs

This clears the request log files.

>**Note:** The full set of logs for this user is deleted with this call. Individual logs may not be deleted.

## URL

    /diagnostics/request_logs

## HTTP Method

   GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/diagnostics/request_logs
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response
 
    The response returns a success or failure.
