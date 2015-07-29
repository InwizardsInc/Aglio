# Get Brand Profile Information

This returns a list of brand profiles associated with the account and the default brand profiles.
The Account Branding feature (accountSettings “canSelfBrandSend” and “canSelfBrandSend” are true)
must be enabled for the account to use this.

## URL

    /accounts/{accountId}/brands

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/brands
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>
                               {integrator_key}</IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of brand profiles associated with the account and the default sending and signing brand profile.

The following example shows the response json body.

### Example Request Body

    {
      "brands":[
        {
          "brandCompany":"String content"
          "brandId":"String content",
          "brandName":"String content"
        },
        {
          "brandCompany":"String content"
          "brandId":"String content",
          "brandName":"String content"
        }
      ]
      "recipientBrandIdDefault":"String content",
      "senderBrandIdDefault":"String content",
    }
