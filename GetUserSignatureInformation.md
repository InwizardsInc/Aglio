# Get User Signature Information

This returns the structure of a single signature with a known signature name.

## URL

    /accounts/{accountId}/users/{userId}/signatures/{signatureIdOrName}

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account.
> 
> The {signatureIdOrName} accepts signature ID or signature name. DocuSign recommends you use signature ID (signatureId), since some names contain characters that don’t properly URL encode. If you use the user name, it is likely that the name includes spaces and you might need to URL encode the name before using the URL. For example: "Bob Smith" to "Bob%20Smith"

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/signatures/{signatureIdOrName}
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>

## Response

The response returns information for the request user signature.

### Example Response Body

    {
      "signatureId":"String content",
      "adoptedDateTime":"String content",
      "createdDateTime":"String content",
      "initialsImageUri":"String content",
      "signatureFont":"String content",
      "signatureImageUri":"String content",
      "signatureInitials":"String content",
      "signatureName":"String content",
      "signatureType":"String content",
      "signature150ImageId":"String content",
      "initials150ImageId":"String content",
      "isDefault": "String content"
    }
