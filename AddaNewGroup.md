# Add a New Group

This adds one or more groups for the account.

Groups can be used to help manage users by associating users with a group.
A group can be associated with a Permission Profile, which sets the user permissions
for users in that group without having to set the userSettings for each user. You are not
required to set Permission Profiles for a group, but this makes it easier to manage user permissions
for a large number of users. Groups can also be used with template sharing to limit user access to templates.

## URL

    /accounts/{accountId}/groups

## HTTP Method

    POST

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|groupName|Yes|String|The name for the new user group.|
|permissionProfileId|No|String|The ID number of the permission profile that the group is associated with. See [Get a List of Permission Profiles](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Get%20a%20List%20of%20Permission%20Profiles.htm) for information on retrieving a list of IDs.|

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/groups
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "groups":[{
        "groupName":"String content",
        "permissionsProfileId":"String content"
      }]
    }

## Response

The response returns if the API execution is successful (201 – Created) or failed.
The response contains a group structure similar to the request and includes the groupId
assigned to the group. If an error occurred during the POST operation for any of the groups,
that group will contain an errorDetails node with an errorCode and message.

The following example shows the response json body.

### Example Response Body

    {
      "groups":[{
        "errorDetails":{
          "errorCode":"String content",
         "message":"String content"
        },
        "groupId":"String content",
        "groupName":"String content",
        "groupType":"String content",
        "permissionsProfileId":"String content"
      }]
    }
