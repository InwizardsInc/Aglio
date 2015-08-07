# Delete Custom User Settings

This deletes the specified custom user settings for a single user.

### Deleting Grouped Custom User Settings

If the custom user settings you want to delete are grouped, you must include the following information in the header, after Content-Type, in the request:

    X-DocuSign-User-Settings-Key:group_name

Where the group_name is your designated name for the group of customer user settings.

If the extra header information is not included, only the custom user settings that were added without a group are deleted.

## URL

    /accounts/{accountId}/users/{userId}/custom_settings

## HTTP Method

    DELETE

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|customSettings|Yes|String|The name/value pair information for the user custom setting.|

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/custom_settings
    
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

## Response

The response returns a success or failure and the list of the custom name/value pairs that were deleted.

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
