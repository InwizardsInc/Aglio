# Modify Account Settings

This updates the account settings list for the specified account.

## URL

    /accounts/{accountId}/settings

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|accountSettings||String|The name/value pair information for account settings. These determine the features available for the account. See the [accountSettings list](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Create%20Account.htm#accountS) for more information about the accountSettings.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json
    
    {
      "accountSettings":[{
        "name":"String content",
        "value":"String content"
      }]
    }

## Response

    The response returns a success or failure.
