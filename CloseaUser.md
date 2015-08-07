# Close a User

This closes one or more user records in the account. Users are never deleted from an account, but closing a user prevents them from using account functions.

## URL

    /accounts/{accountId}/users

## HTTP Method

    DELETE

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|userId|Yes|String|The user ID number for user being removed from the account.|
|userName|No|String|The user name for the user being removed from the account.|

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/users
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "users":[{
        "userId":"String content",
        "userName":"String content",
      }]
    }

## Response

The response returns if the API execution is successful (200 – OK) or failed. The response contains a user structure similar to the request and includes the user changes. If an error occurred during the DELETE operation for any of the users, that user will contain an errorDetails node with an errorCode and message.

The following example shows the response json body.

### Example Response Body

    {
      "users":[{
        "errorDetails":{
          "errorCode":"String content",
          "message":"String content"
        },
        "uri":"String content",
        "userpId":"String content",
        "userName":"String content",
        "userStatus":"String content",
        "userType":"String content"
      }]
    }
