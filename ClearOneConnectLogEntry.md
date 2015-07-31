# Clear One Connect Log Entry

This is used to clear (remove) one entry from the Connect Log.

## URL

    /accounts/{accountId}/connect/logs/{logId}

## HTTP Method

    DELETE

## Parameters

    No additional parameters are required.

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect/logs/{logId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

    The response returns a success or failure message.
