# Remove a User Social Account

This removes a social account from a user’s account.

## URL

    /accounts/{accountId}/users/{userId}/social

## HTTP Method

    DELETE

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|provider|Yes|String|The name of the social account provider (Google, Facebook, Yahoo, etc.).|
|email|Yes|String|The user’s email address for the social account.|
|userName|Yes|String|The full user name in the social account.|

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/social
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "provider":"String content",
      "email":"String content",
      "userName":"String content"
    }

## Response

    The response returns if the API execution is successful (200 – OK) or failed.
