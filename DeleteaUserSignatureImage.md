# Delete a User Signature Image

This deletes a specific user signature image.

>**Note:** The user initials image associated with this user is not deleted.

## URL

    /accounts/{accountId}/users/{userId}/signatures/{signatureIdOrName}/signature_image

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account. 
>
>The {signatureIdOrName} accepts signature ID or signature name. DocuSign recommends you use signature ID (signatureId), since some names contain characters that don’t properly URL encode. If you use the user name, it is likely that the name includes spaces and you might need to URL encode the name before using the URL. For example: "Bob Smith" to "Bob%20Smith"

## HTTP Method

    DELETE

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/
    {userId}/signatures/{signatureIdOrName}/signature_image
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>

## Response

The response returns a success or failure and information about the user signature and initials.

The following example shows the response json body.

### Example Response Body

    {
      "adoptedDateTime":"String content",
      "createdDateTime":"String content",
      "initials150ImageId":"String content",
      "initialsImageUri":"String content",
      "signature150ImageId":"String content",
      "signatureFont":"String content",
      "signatureId":"String content",
      "signatureImageUri":"String content",
      "signatureInitials":"String content",
      "signatureName":"String content",
      "signatureType":"String content"
    }
