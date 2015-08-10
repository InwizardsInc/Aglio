# Get a List of User Signature Definitions

This returns the signature definitions for the specified user.

## URL

    /accounts/{accountId}/users/{userId}/signatures

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account.
> Since the {signatureName} is a string name of a user that likely includes spaces, you might need to URL encode the signatureName before using the URL.
> For example: "Bob Smith" to "Bob%20Smith"

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/signatures
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>

## Response

The response returns a list of signatures for the user.

### Example Response Body

    {
      "userSignatures":[{
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
      },
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
      ]
    }
 
