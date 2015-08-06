# Share a Template with a Group

This shares a template with a group.

## URL

    /accounts/{accountId}/templates/{templateId}/groups

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|groupId|Yes|String|The group ID number.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/templates/{templateId}/groups
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "groups":[{
        "groupId":"String content",
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
