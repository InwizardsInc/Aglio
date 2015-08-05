# Add Group Brand ID Information

This adds brand information to a group.

## URL

    /accounts/{accountId}/groups/{groupId}/brands

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|String|
|----|---------|----|------|
|brandId|Yes|String|The brandId of the brand profile being added to the group.|
|brandName|Yes|String|The brand name associated with the brand profile.|
|brandCompany|Yes|String|The brand company associated with the brand profile.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/groups/{groupId}/brands
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "brands":[{
        "brandId":"String content",
        "brandName":"String content",
        "brandCompany":"String content"
      }]
    }

## Response

The response returns as success or failure, along with the brand information (brandId, brandName, and brandCompany) added to the group.

The following example shows the response json body.

### Example Response Body

    {
      "brands":[{
        "brandId":"String content",
        "brandName":"String content",
        "brandCompany":"String content"
      }]
    }
