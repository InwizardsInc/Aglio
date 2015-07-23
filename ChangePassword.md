# Change Password

This changes the password for a user.

## URL

    /login_information/password

## Formats

    XML, JSON

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Descrption|
|-----|-----|-----|-----|
|currentPassword|Yes|String|The user’s current password|
|email|Yes|String|The user’s email address for the associated account.|
|forgottenPasswordInfo|No|String|A complex element that has up to four Question/Answer pairs for forgotten password information.|
|newPassword|Yes|String|The user’s new password.|

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/login_information/password
    
    X-DocuSign-Authentication:<DocuSignCredentials><Username>{name}
                              </Username><Password>{password}</Password>
                              <IntegratorKey>{integrator_key}</IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "currentPassword": "String content",
      "email": "String content",
      "forgottenPasswordInfo": {
         "forgottenPasswordAnswer1": "String content",
          "forgottenPasswordAnswer2": "String content",
          "forgottenPasswordAnswer3": "String content",
          "forgottenPasswordAnswer4": "String content",
          "forgottenPasswordQuestion1": "String content",
          "forgottenPasswordQuestion2": "String content",
          "forgottenPasswordQuestion3": "String content",
          "forgottenPasswordQuestion4": "String content"
      },
    "newPassword": "String content"
    }

## Response

    The response returns a success or failure.
