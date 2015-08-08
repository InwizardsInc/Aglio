# Modify User Profile Image

This uploads an image to the user profile. The supported image formats for this file are: gif, png, jpeg, and bmp. The file must be less than 200K.. For best viewing results, DocuSign recommends that the image is no more than 79 pixels wide and high.

## URL

    /accounts/{accountId}/users/{userId}/profile/image

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account.

## HTTP Method

    PUT

## Parameters

The only item needed is the image.

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/profile/image
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Content-Type: image/x-ms-bmp
    
    <image removed>

## Response

    The response returns a success or failure.
