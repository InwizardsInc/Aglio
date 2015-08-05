# Modify Group Information

This lets you modify a group name and modify, or set, the permission profile for the group.

## URL

    /accounts/{accountId}/groups

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|groupId|Yes|String|The group ID number.|
|groupName|No|String|The new name for the user group.|
|permissionProfileId|No|String|The ID number of the permission profile that the group is associated with. See [Get a List of Permission Profiles](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Get%20a%20List%20of%20Permission%20Profiles.htm) for information on retrieving a list of IDs.|

## Response

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/groups
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                                <Password>{password}</Password><IntegratorKey>{integrator_key}
                                </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "groups":[{
        "groupId":"String content",
        "groupName":"String content",
        "permissionsProfileId":"String content"
      }]
    }

## Response

The response returns if the API execution is successful (200 – OK) or failed.
The response contains a group structure similar to the request. If an error occurred
during the PUT operation for any of the groups, that group will contain an errorDetails
node with an errorCode and message.

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
