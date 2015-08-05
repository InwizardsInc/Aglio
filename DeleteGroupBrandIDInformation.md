# Delete Group Brand ID Information

This removes brand information from the requested group.

## URL

    /accounts/{accountId}/groups/{groupId}/brands

## HTTP Method

    DELETE

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|brandId|Yes|String|The brandId of the brand profile being removed from the group.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/groups/{groupId}/brands
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
       "brands":[{
        "brandId":"String content"
      },
        "brandId":"String content"
      }]
    }

## Response

The response returns as success or failure, along with the brandIds of the brands removed from the group.

The following example shows the response json body.

### Example Response Body

    {
      "brands":[{
        "brandId":"String content"
      },
      {
        "brandId":"String content"
      }]
    }
