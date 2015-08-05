# Get a List of Permission Profiles

This retrieves list of Permission Profiles. Permission Profiles are a standard set of user permissions that can be applied to individual users or users in a Group. This makes it easier to manage user permissions for a large number of users, without having to change permissions on a user-by-user basis.

Currently Permission Profiles can only be created and modified in the DocuSign console.

## URL

    /accounts/{accountId}/permission_profiles

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/permission_profiles
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of permission profiles for the account.

The following example shows the response json body.

### Example Response Body

    {
      "permissionProfiles":[
       {
          "permissionProfileId":"String content",
          "permissionProfileName":"String content"
        },
        {
          "permissionProfileId":"String content",
          "permissionProfileName":"String content"
        },
      ]
    }
