# Get Group Information

This retrieves information about groups associated with the account.

## URL

    /accounts/{accountId}/groups

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/groups
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the information for the groups associated with the account.

The following example shows the response json body.

### Example Response Body

    {
      "groups":[{
        "groupId":"String content",
        "groupName":"String content",
        "groupType":"String content",
        "permissionsProfileId":"String content"
      }]
    }
