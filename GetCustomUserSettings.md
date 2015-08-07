# Get Custom User Settings

This retrieves a list of custom user settings for a single user.

Custom settings are a flexible way to store and retrieve custom user information that can be used in your own system.

>**Note:** Custom user settings are not the same as user account settings.

### Getting Grouped Custom User Settings

If the custom user settings you want to retrieve are grouped, you must include the following information in the header, after Content-Type, in the request:

    X-DocuSign-User-Settings-Key:group_name

Where the group_name is your designated name for the group of customer user settings.

If the extra header information is not included, only the custom user settings that were added without a group are retrieved.

## URL

    /accounts/{accountId}/users/{userId}/custom_settings

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/custom_settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the list of the custom name/value pairs for the specified user that are not in a group.

The following example shows the response json body.

### Example Response Body

    {
      "customSettings":[{
        "name":"String content",
        "value":"String content",
      },
      {
        "name":"String content",
        "value":"String content"
      }]
    }
