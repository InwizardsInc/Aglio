# Get User Social Accounts

This returns a list of social accounts linked to a user’s account.

## URL

    /accounts/{accountId}/users/{userId}/social

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/social
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the list of social account information for the user and the userId for the user.

The following example shows the response json body.

### Example Response Body

    {
      "socialAccountInformation":[{
        "email":"String content",
        "provider":"String content",
        "socialId":"String content",
        "userName":"String content"
      },
      {
        "email":"String content",
        "provider":"String content",
        "socialId":"String content",
        "userName":"String content"}],
      }],
      "userId":"String content"
    }
