# Add Users to a Group

This adds one or more users to an existing group.

## URL

    /accounts/{accountId}/groups/{groupId}/users

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|userId|Yes|String|The user ID number for a user being added to the group.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/groups/{groupId}/users
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "users":[{
        "userId":"String content",
        }]
    }

## Response

The response returns if the API execution is successful (200 – OK) or failed. The response contains a user structure similar to the request and includes the user changes. If an error occurred during the PUT operation for any of the users, that user will contain an errorDetails node with an errorCode and message.

The following example shows the response json body.

### Example Response Body

    {
      "users":[{
        "errorDetails":{
          "errorCode":"String content",
          "message":"String content"
        },
        "uri":"String content",
        "userId":"String content",
        "userName":"String content",
        "userStatus":"String content",
        "userType":"String content"
      }]
    }
