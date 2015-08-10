# Get a User Initials Image

This returns a specific user initials image. The image is returned in the same format as uploaded. In the request you can specify if the chrome (the added line and identifier around the initial image) is returned with the image.

## URL

    /accounts/{accountId}/users/{userId}/signatures/{signatureIdOrName}/initials_image

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account.
>
>The {signatureIdOrName} accepts signature ID or signature name. DocuSign recommends you use signature ID (signatureId), since some names contain characters that don’t properly URL encode. If you use the user name, it is likely that the name includes spaces and you might need to URL encode the name before using the URL. For example: "Bob Smith" to "Bob%20Smith"

Optional request string: include_chrome={true} to include chrome, the default value is false.

>**Note:** Older envelopes might only have chromed images. If getting the non-chromed image fails, try getting the chromed image.

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/
    {userId}/signatures/{signatureIdOrName}/initials_image
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>

## Response

    The response returns the initials image file.
