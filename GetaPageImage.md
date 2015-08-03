# Get a Page Image

This returns a page image for display.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents/
                        {documentId}/pages/{pageId}/page_image
    
    Optional query strings: dpi={dpi for the image}, 
    max_width={maximum width in pixels},
    max_height={maximum height in pixels}

## HTTP Method

    GET

## Parameters

There are no required parameters, but the following query
string parameters can be added to change the page image settings.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|dpi|No|String|Sets the dpi for the image.|
|max_width|No|String|Sets the maximum width for the page image in pixels. The dpi is recalculated based on this setting.|
|max_height|No|String|Sets the maximum height for the page image in pixels. The dpi is recalculated based on this setting.|

## Request

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/
    envelopes/{envelopeId}/documents/{documentId}/pages/{pageId}/page_image
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

    The response returns the requested page image with the requested settings.
