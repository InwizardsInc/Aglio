# Add or Modify Custom User Settings

This allows you to add or update custom user settings for a single user.

>**Note:** Custom user settings are not the same as user account settings.

Custom settings are a flexible way to store and retrieve custom user information that can be used in your own system.

>**Important:** There is a limit on the size for all the custom user settings for a single user. All the custom user settings for a single user is limited to 4,000 characters, which includes the xml and json structure for the settings.

### Grouping Custom User Settings

In addition to adding the custom user settings, you can group the settings when adding them. Grouping allows you to retrieve only those settings that are in a group, instead of retrieving all the user custom settings.

To group custom user settings, add the following information in the header, after Content-Type:

    X-DocuSign-User-Settings-Key:group_name

Where the group_name is your designated name for the group of customer user settings. Grouping is shown in the Example Request Body below.

When getting or deleting grouped custom user settings, the extra header information must be included.

Grouping custom user settings is not required and if the extra header information is not included, the custom user settings are added normally and can be retrieved or deleted without including the additional header.

## URL

    /accounts/{accountId}/users/{userId}/custom_settings

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|customSettings|Yes|String|The name/value pair information for the user custom setting.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/custom_settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    X-DocuSign-User-Settings-Key:group_name
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

## Reqponse

The response returns a success or failure message and a list of the added or updated user custom settings.

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
