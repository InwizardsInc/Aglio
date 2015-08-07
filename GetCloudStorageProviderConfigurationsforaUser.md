# Get Cloud Storage Provider Configurations for a User

This retrieves the list of cloud storage providers enabled for the account and the configuration information for the user.

## URL

    /accounts/{accountId}/users/{userId}/cloud_storage
    Optional query parameter: redirectUrl={someURL}

## HTTP Method

    GET

## Parameters

There are no required parameters, but the following optional query parameter can be added to the request.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|redirectUrl|No|String|The URL the user is redirected to after the cloud storage provider authenticates the user. Using this will append the redirectUrl to the authenticationUrl.<br/>The redirectUrl is restricted to URLs in the docusign.com or docusign.net domains.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountid}/users/{userid}/cloud_storage
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response provides a list of the cloud storage providers for the user and shows if the user has passed authentication with provider.

|Value|Desription|
|-----|----------|
|serviceId|The DocuSign generated ID for the cloud storage provider. This information is only included in the response if the user has passed authentication for the cloud storage provider.|
|service|The service name for the cloud storage provider.|
|authenticationUrl|The authentication URL used for the cloud storage provider. This information is only included in the response if the user has not passed authentication for the cloud storage provider. If the redirectUrl query string is provided, the returnUrl is appended to the authenticationUrl.|

### Example Response Body

    {
      "storageProviders": [
        {
          "serviceId": "4136",
          "service": "DropBox"
        },
        {
          "service": "Box",
          "authenticationUrl": "BoxAuthenticationUrl"
        }
      ]
    }
