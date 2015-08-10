# Close a User Signature

This removes the signature information for the user.

## URL

    /accounts/{accountId}/users/{userId}/signatures/{signatureIdOrName}

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account.
>
> The {signatureIdOrName} accepts signature ID or signature name. DocuSign recommends you use signature ID (signatureId), since some names contain characters that don’t properly URL encode. If you use the user name, it is likely that the name includes spaces and you might need to URL encode the name before using the URL. For example: "Bob Smith" to "Bob%20Smith"

## HTTP Method

    DELETE

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/signatures/{signatureIdOrName}
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>

## Response

    The response returns a success or failure.
