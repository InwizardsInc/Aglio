# Get Group Brand ID Information

This returns information about the brands associated with the requested group.

## URL

    /accounts/{accountId}/groups/{groupId}/brands

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/groups/{groupId}/brands
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the brand information (brandId, brandName, and brandCompany) associated with the group.

The following example shows the response json body.

### Example Response Body

    {
      "brands":[{
        "brandId":"String content",
        "brandName":"String content",
        "brandCompany":"String content"
      },
      {
        "brandId":"String content",
        "brandName":"String content",
        "brandCompany":"String content"
      }]
    }
