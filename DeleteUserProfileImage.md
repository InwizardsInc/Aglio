# Delete User Profile Image

This removes the image from the user profile.

## URL

    /accounts/{accountId}/users/{userId}/profile/image

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account.

## HTTP Method

    DELETE

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    DELETE https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/profile/image
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>

## Response

    The response returns a success or failure.
