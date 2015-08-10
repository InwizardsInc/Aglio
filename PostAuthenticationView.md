# Post Authentication View

This provides a URL to start the authentication view of the DocuSign UI.

## URL

    /accounts/{accountId}/views/console

## HTTP Method

    POST

## Parameters

No parameters are required, but an optional envelopeId can be included in the request.

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/views/console
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the authentication view url.

The following example shows the header followed by the response json body.

### Example Response Body

    {
      "url":"String content"
    }
