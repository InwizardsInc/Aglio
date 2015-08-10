# Create an Authorization Token

This creates an OAuth2 authorization server token endpoint.

## URL

    /oauth2/token

## HTTP Method

    POST

## Parameters

The call uses a request with the

## Request

### Example Request Body

    POST https://{server}/restapi/{apiVersion}/oauth2/token
    
    Accept: application/json
    Content-Type: application/x-www-form-urlencoded
    grant_type=password&client_id={integrator_key}&username={name}&password={password}&scope=api

## Response

The response returns if the API execution is successful (200 – OK) or failed. If successful, the response will contain the server token information.

|Name|Description|
|----|-----------|
|access_token|Access token information.|
|scope|This should always be “api”|
|token_type|This should always be “bearer”|

<br/>The following example shows the response json body.<br/>

### Example Response Body

    {
      "access_token":"String content",
      "scope":"String content",
      "token_type":"String content"
    }
