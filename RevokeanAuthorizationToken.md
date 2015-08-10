# Revoke an Authorization Token

This revokes an OAuth2 authorization server token. After this is done, a caller must re-authenticate to restore access.

## URL

    /oauth2/revoke

## HTTP Method

    POST

## Parameters

The call must have “token_type” and “access_token” for the server token to be revoked in the Authorization.

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/oauth2/revoke
    
    Authorization:<token_type><access_token>
    
    Accept: application/json
    Content-Type: application/json

## Response

    The response returns if the API execution is successful (200 – OK) or failed.
