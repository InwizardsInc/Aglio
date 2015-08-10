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
