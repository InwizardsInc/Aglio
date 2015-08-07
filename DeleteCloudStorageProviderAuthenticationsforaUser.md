# Delete Cloud Storage Provider Authentications for a User

This removes the user authentication information for one or more cloud storage providers. The next time the user tries to access the cloud storage provider, they must pass normal authentication.

## URL

    /accounts/{accountId}/users/{userId}/cloud_storage

## HTTP Method

    DELETE

## Parameters

Either service or serviceId must be included. Using “all” in service or serviceId deletes the user authentication information for all cloud storage providers.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|serviceId|Yes*|String|The DocuSign generated ID for the cloud storage provider.|
|service|Yes*|String|The service name for the cloud storage provider.|

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountid}/users/{userid}/cloud_storage
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "storageProviders": [
        {
          "serviceId": "4136"
        },
        {
          "service": "Box"
        }
      ]
    }
