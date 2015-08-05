# Get List of Users in a Group

This retrieves a list of users in a group.

##  URL

    /accounts/{accountId}/groups/{groupId}/users

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/groups/{groupId}/users
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the information for the users in the group.

The following example shows the response json body.

### Example Response Body

    {
      "users":[{
        "uri":"String content",
        "email":"String content",
        "userId":"String content",
        "userName":"String content",
        "userStatus":"String content",
        "userType":"String content"
      }]
    }}
