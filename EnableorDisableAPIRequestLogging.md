# Enable or Disable API Request Logging

This enables or disables API request logging for troubleshooting.

When enabled (apiRequestLogging is true), REST API requests and responses for the user are added to a log. There are additional calls to download the log files (individually or as a zip file) and to clear the log by deleting current entries. A log can have up to 50 requests/responses and the current number of log entries can be determined by getting the settings. Logging is automatically disabled when the log limit of 50 is reached.

Private information, such as passwords and integrator key information, which is normally located in the call header is omitted from the request/response log.

>**Note:** API request logging only captures requests from the authenticated user. Any call that does not authenticate the user and resolve a userId isn't logged. Meaning that login_information, NewAccounts or other distributor-credential calls are not logged.

## URL

    /diagnostics/settings

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|apiRequestLogging|Yes|String|This enables (true) or disables (false) API request logging for the user.|


##  Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/diagnostics/settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "apiRequestLogging": "true"
    }

## Response

The response returns a success or failure, along with the current API request logging settings for the user.

### Example Response Body

    {
      "apiRequestLogging": "true",
      "apiRequestLogMaxEntries": "50",
      "apiRequestLogRemainingEntries": "50"
    }
