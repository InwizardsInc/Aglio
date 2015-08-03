# Rotate Page Image

This rotates a page image for display. The page image can be rotated to the left or right.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents/
    {documentId}/pages/{pageId}/page_image

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|rotate|Yes|String|Sets the direction the page image is rotated. The possible settings are: left or right|

## Request

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/
    {envelopeId}/documents/{documentId}/pages/{pageId}/page_image
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "rotate":"String content"
    }

## Response

    The response a success or failure.
