# Delete Captive Recipient Signature

This deletes the signature for one or more captive recipient records;
it is primarily used for testing. This provides a way to reset the signature
associated with a clientUserId so a new signature can be created the next time the clientUserId is used.

## URL

    /accounts/{accountId}/captive_recipients/signature

## HTTP Method

    DELETE

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|Email|Yes|String|The email address associated with the captive recipient.|
|userName|Yes|String|The user name associated with the captive recipient.|
|clientUserId|Yes|String|The sender created value associated with the captive recipient.|

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/captive_recipients/signature
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json
    
    {
      "captiveRecipients": [
        {
          "email": "String content",
          "userName": " String content",
          "clientUserId": " String content"
        },
        {
          "email": " String content",
          "userName": " String content",
          "clientUserId": " String content"
        }
      ]
    }

## Response

The response returns success or failure and any error messages.

The following example shows the response json body.

### Example Response Body

    {
      "captiveRecipients": [
        {
          "email": "sample string",
          "userName": "sample string",
          "clientUserId": "sample string",
          "errorDetails": {
            "errorCode": "sample string",
            "message": "sample string"
          }
        },
        {
          "email": "sample string",
          "userName": "sample string",
          "clientUserId": "sample string",
          "errorDetails": {
            "errorCode": "sample string",
            "message": "sample string"
          }
        }
      ]
    }
