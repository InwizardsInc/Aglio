# Get User Information

This retrieves the user information for specified user.

## URL

    /accounts/{accountId}/users/{userId}
    Optional query string: additional_info={true/false}

## HTTP Method

    GET

## Parameters

There are no required parameters, but the following optional query can be added to provide additional information in the response.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|additional_info|No|Boolean|When true, the full list of user information is returned for the user. This includes when a user last logged on to the system, when the user’s password will expire (if the account has set expiration times), and the user’s current password status in the response.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the user information.

If the query string additional_info=true is included, the following user information is included in the response.

|Name|Type|Description|
|----|----|-----------|
|passwordExipration|String|Shows the date-time when the user’s password will expire. If the account Password Strength Settings – Expiration information is not set, this value is not returned.|
|lastLogin|String|Shows the date-time when the user last logged on to the system.|
|loginStatus|String|Shows the current status of the user’s password. Possible values are:<ul><li>password_reset</li><li>password_active</li><li>password_expired</li><li>password_locked</li><li>password_reset_failed</li></ul>|

The following example shows the response json body with the query string additional_info=true.

### Example Response Body

    {
      "userName": "String content",
      "userId": "String content",
      "userType": "String content",
      "isAdmin": "String content",
      "userStatus": "String content",
      "uri": "String content",
      "email": "String content",
      "password": "String content",
      "title": "String content",
      "createdDateTime": "String content",
      "firstName": "String content",
      "middleName": "String content",
      "lastName": "String content",
      "suffixName": "String content",
      "userSettings": [
        {
          "name": "String content",
          "value": "String content"
        }
      ],
      "sendActivationOnInvalidLogin": "String content",
      "activationAccessCode": "String content",
      "enableConnectForUser": "String content",
      "forgottenPasswordInfo": {
        "forgottenPasswordQuestion1": "String content",
        "forgottenPasswordAnswer1": "String content",
        "forgottenPasswordQuestion2": "String content",
        "forgottenPasswordAnswer2": "String content",
        "forgottenPasswordQuestion3": "String content",
        "forgottenPasswordAnswer3": "String content",
        "forgottenPasswordQuestion4": "String content",
        "forgottenPasswordAnswer4": "String content"
      },
      "groupList": [
        {
          "groupId": "String content",
          "groupName": "String content",
          "permissionProfileId": "String content",
          "groupType": "String content",
        }
      ],
      "workAddress": {
        "address1": "String content",
        "address2": "String content",
        "city": "String content",
        "stateOrProvince": "String content",
        "postalCode": "String content",
        "phone": "String content",
        "fax": "String content",
        "country": "String content"
      },
      "homeAddress": {},
      "loginStatus": "String content",
      "passwordExpiration": "String content",
      "lastLogin": "String content",
      "customSettings": [
        {}
      ]
      "profileImageUri": "String content",
      "userProfileLastModifiedDate": " String content",
      "signatureImageUri": " String content",
      "initialsImageUri": " String content"
    }
