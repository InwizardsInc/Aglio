# Delete a Connect Configuration

This allows you to delete one DocuSign Connect configuration.

>**Note:** Connect must be enabled for your account to use this function.

## URL

    /accounts/{accountId}/connect/{connectId}

## HTTP Method

    DELETE

## Parameters

    No additional parameters are required.

## Request

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect/{connectId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

    The response returns a success or failure.
