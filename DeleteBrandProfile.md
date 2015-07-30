# Delete Brand Profile

This deletes one or more brand profiles from an account.
The Account Branding feature (accountSettings “canSelfBrandSend” and “canSelfBrandSend” are true)
must be enabled for the account to use this.

## URL

    /accounts/{accountId}/brands

## HTTP Method

    DELETE

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|brandId&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Yes&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|String&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|The brandId to be deleted from the account.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/brands
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>
                               {integrator_key}</IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json
    
    {
      "brands":[
        {"brandId":"String content"},
        {"brandId":"String content"}
      ]
    }

## Response

The response returns the success (200 – OK) or failure, along with a list of deleted brand IDs.

The following example shows the response json body.

### Example Response Body

    {
      "brands":[
        {"brandId":"String content"},
        {"brandId":"String content"}
      ]
    }
