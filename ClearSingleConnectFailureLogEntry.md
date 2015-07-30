# Clear a Connect Failure Log Entry

This is used to clear (remove) the Connect Failure Log information for one entry.

## URL

    /accounts/{accountId}/connect/failures/{failureId}

## HTTP Method

    DELETE

## Parameters

    No additional parameters are required.

## Request

## Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect/failures/{failureId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

    The response returns a success or failure message.
