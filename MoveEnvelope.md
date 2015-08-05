# Move Envelope

This moves an envelope from its current folder to selected folder.

>**Note:** This can be used to delete envelopes by using “recyclebin” as
> folderId. Placing an in process envelope (envelope status of sent or delivered)
> in the recycle bin will void the envelope. This can also be used to delete templates
> by using the templateId in place of the envelopeId and using “recyclebin” as folderId.

## URL

    /accounts/{accountId}/folders/{folderId}

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|envelopeIds|Yes|String|The envelope ID for the envelope that is being moved.|
|fromFolderId|No|String|The folder ID the envelope is being moved from.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/folders/{folderId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "envelopeIds": ["String"],
      "fromFolderId": "FolderId"
    }

## Response

    The response returns if the move was a success or failure.
