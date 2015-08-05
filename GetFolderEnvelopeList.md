# Get Folder Envelope List

Returns a list of the envelopes in the specified folder. You can narrow the query by adding some optional items.

## URL

    /accounts/{accountId}/folders/{folderId}
    Optional query additions: start_position={ integer}, from_date = {date/time},
    to_date= {date/time}, search_text={text}, status={envelope status}, owner_name={username}, owner_email={email}

## HTTP Method

    GET

## Parameters

No additional parameters are required, but the following optional query strings can be added to narrow the response results.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|start_position|No|Integer|The position of the folder items to return. This is used for repeated calls, when the number of envelopes returned is too much for one return (calls return 100 envelopes at a time). The default value is 0.|
|from_date|No|date\Time|Only return items on or after this date. If no value is provided, the default search is the previous 30 days.|
|to_date|No|date\Time|Only return items up to this date. If no value is provided, the default search is to the current date.|
|search_text|No|String|The search text used to search the items of the envelope. The search looks at recipient names and emails, envelope custom fields, sender name, and subject.|
|status|No|Status|The current status of the envelope. If no value is provided, the default search is all/any status.|
|owner_name|No|username|The name of the folder owner.|
|owner_email|No|email|The email of the folder owner.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/folders/{folderId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the list of envelope in the folder that meet the query information.

The following example shows the response json body.

### Example Response Body

    {
      "endPosition": "1",
      "folderItems": [{
        "createdDateTime": "String content",
        "envelopeId": "String content",
        "envelopeUri": "String content",
        "ownerName": "String content",
        "senderEmail": "String content",
        "senderName": "String content",
        "sentDateTime": "String content",
        "status": "String content",
        "subject": "String content"
      },
      {
        "createdDateTime": "String content",
        "envelopeId": "String content",
        "envelopeUri": "String content",
        "ownerName": "String content",
        "senderEmail": "String content",
        "senderName": "String content",
        "sentDateTime": "String content",
        "status": "String content",
        "subject": "String content"
      }],
      "resultSetSize": "2",
      "startPosition": "0"
    }
