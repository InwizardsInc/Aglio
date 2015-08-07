# Add Cloud Storage Provider Return Information for a User

This configures the redirect URL information added to the authentication URL for one or more cloud storage providers for a user.

## URL

    /accounts/{accountId}/users/{userId}/cloud_storage

## HTTP Method

    POST

## Parameters

There are no required parameters, but the following optional query parameter can be added to the request.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|service|Yes|String|The service name for the cloud storage provider.|
|redirectUrl|No|String|The URL the user is redirected to after the cloud storage provider authenticates the user. This value is appended to the authenticationUrl for the cloud storage provider.<br/>The redirectUrl is restricted to URLs in the docusign.com or docusign.net domains.|

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountid}/users/{userid}/cloud_storage
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "storageProviders": [
        {
          "service": "string",
          "redirectUrl": "string"
        },
        {
          "service": "string",
          "redirectUrl": "string"
        }
      ]
    }

## Response

The response returns a success or failure, along with the serviceId and authenticationUrl for the cloud storage providers.

The following example shows the response json body.

### Example Response Body

    {
      "storageProviders": [
        {
          "serviceId": "4136",
          "service": "DropBox"
          "authenticationUrl": "DropBoxAuthenticationUrl"
        },
        {
          "serviceId": "4137",
          "service": "Box",
          "authenticationUrl": "BoxAuthenticationUrl"
        }
      ]
    }
