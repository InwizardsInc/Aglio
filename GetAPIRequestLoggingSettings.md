# Get API Request Logging Settings

This retrieves the current API request logging setting for the user and remaining log entries.

## URL

    /diagnostics/settings

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/diagnostics/settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the current API request logging setting for the user, along with the maximum log entries and remaining log entries.

### Example Response Body

    {
      "apiRequestLogging": "true",
      "apiRequestLogMaxEntries": "50",
      "apiRequestLogRemainingEntries": "50"
    }
