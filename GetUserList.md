# Get User List

This returns a list of users for the specified account.

## URL

    /accounts/{accountId}/users
    Optional query additions: additional_info={true/false}

## HTTP Method

    GET

## Parameters

There are no required parameters, but the following optional query can be added to provide additional information in the response.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|additional_info|No|Boolean|When true, the full list of user information is returned for each user in the account.|

## Response

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/users
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the list of users for the specified account. If the additional_info query was added to the URL and set to true, the full user information is returned for each user.

The following example shows the response json body.

### Example Response Body

    {
      "users": [
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
              "groupType": "String content"
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
          "lastLogin": "String content"
          "customSettings": [
              {}
            ]
            "profileImageUri": "String content",
            "userProfileLastModifiedDate": " String content",
            "signatureImageUri": " String content",
            "initialsImageUri": " String content"
        }
      ]
    }
