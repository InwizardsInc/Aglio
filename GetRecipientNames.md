# Get Recipient Names

This returns a list of recipients that are available for the given email address.

## URL

    /accounts/{accountId}/recipient_names
    The query string email = {email} is required.

## HTTP Method

    GET

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|email|Yes|String|The email address for the user|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/recipient_names?email={email}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the recipient names associated with the email is used by more than one user.

### Example Response Body

    {
      "multipleUsers": "false",
      "recipientNames": [
        "Resty B. Tester",
        "Resty Tester",
        "Resty Tester III"
      ],
      "reservedRecipientEmail": "false"
    }
