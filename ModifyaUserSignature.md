# Modify a User Signature

This creates or modifies the signature font and initials for an existing signature. When creating a signature, you would use this resource to create the signature name and then put the signature and initials images into the signature.

>**Note:** This will also create a default signature for the user when one does not exist.

## URL

    /accounts/{accountId}/users/{userId}/signatures/{signatureIdOrName}
    Optional query string: close_existing_signature={true or false} when true, this will close the current signature.

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account.
> The {signatureIdOrName} accepts signature ID or signature name. DocuSign recommends you use signature ID (signatureId), since some names contain characters that don’t properly URL encode. If you use the user name, it is likely that the name includes spaces and you might need to URL encode the name before using the URL. For example: "Bob Smith" to "Bob%20Smith"

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|signatureFont|No|String|The font type for the signature, if the signature is not drawn.<br/>The supported font types are: "7_DocuSign", "1_DocuSign", "6_DocuSign", "8_DocuSign", "3_DocuSign", "Mistral", "4_DocuSign", "2_DocuSign", "5_DocuSign", "Rage Italic"|
|signatureId|No|String|The signature ID associated with the signature name. The signatureId can be used in the URI in place of the signatureName, and the signatureName in the body will be used. This allows the use of special characters (such as “&”, “<”, “>”) in a signatureName. Note that with each update to signatures, the returned signautreId might change, so the caller will need to trigger off the signatureName to get the new signatureId.|
|signatureInitials|No|String|The initials associated with the signature.|
|signatureName|No|String|The user signature name.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/signatures/{signatureIdOrName}
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "signatureFont":"String content",
      "signatureId":"String content",
      "signatureInitials":"String content",
      "signatureName":"String content"
    }

## Response

The response returns a success or failure and signature name information.

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
