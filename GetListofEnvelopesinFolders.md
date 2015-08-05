# Get List of Envelopes in Folders

This returns a list of envelopes that match the criteria specified in the query.

## URL

    /accounts/{accountId}/search_folders/{search_folder}
    Optional query additions: start_position={integer}, count={integer},
    from_date={date/time}, to_date={date/time}, order_by={string},
    order={string}, include_recipients={true/false}, all

>**Note:** If the userId of the user making the call is the same as the userId for any returned recipient,
> then the userId is added to the returned information for those recipients.

## HTTP Method

    GET

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|search_folder|Yes|String|Specifies the envelope group that is searched by the request. These are logical groupings, not actual folder names. Valid values are listed table below.|
|start_position|No|Integer|Starting value for the list.|
|count|No|Integer|Number of records to return in the cache. The number must be greater than 1 and less than or equal to 100.|
|from_date|No|Date\Time|Start of the date range. If no value is provided, the default search is the previous 30 days.|
|to_date|No|Date/Time|End of the date range.|
|order_by|No|String|Column used to sort the list. Valid values are listed in the table below.|
|order|No|String|Direction order used to sort the list. Valid values are:<br/><ul><li>asc = ascending sort order (a to z)</li><li>desc = descending sort order (z to a)</li></ul>|
|include_recipients|No|True/False|When true, the recipient information is returned in the response.|
|all|No|N/A|This returns all envelopes that matches the criteria.|

search_folder values

|Name|Description|
|----|-----------|
|drafts|Drafts<br/>Note that Draft envelopes are only held for 30 days before they are removed from the system.|
|awaiting_my_signature|Envelopes awaiting the users’ signature.|
|completed|Envelopes with the status of “completed”.|
|out_for_signature|Sent envelopes that have not been completed.|

order_by values

|Name|Description|
|----|-----------|
|action_required|Awaiting|
|created|Date/Time envelope was created.|
|completed|Date/Time envelope was completed.|
|sent|Date/Time envelope was sent.|
|signer_list|List of Signers.|
|status|Envelope status|
|subject|Envelope subject|

## Response

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}}/
    search_folders/{search_folder}?include_recipients=true
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

The response returns the list of envelopes that match the specified criteria.

>**Note:** If the userId of the user making the call is the same as the userId for any returned recipient,
> then the userId is added to the returned information for those recipients.

|Name|Description|
|----|-----------|
|endPosition|The last row id in the result set.|
|folderItems|Collection of folder items in the result set. See the table below for more information on the contents of folder items.|
|nextUri|Provides the Uri to the next chunk of records based on the search request. If the endPosition is the entire results of the search, this is null.|
|previousUri|Provides the Uri to the previous chunk of records based on the search request. If this response is the first response for the search, this is null.|
|resultSetSize|Number of folder items returned in the result set.|
|startPosition|Starting position of the current result set.|
|totalRows|Total number of rows that meet the search criteria. Each row is for a different envelope.|

folderItems

|Name|Description|
|----|-----------|
|completedDateTime|Date/Time the envelope was completed|
|createdDateTime|Date/Time envelope was created|
|envelopeID|Identifier for the envelope|
|envelopeUri|Uri path for the envelope|
|expireDateTime|Date/Time envelope is set to expire|
|folderId|Identifier of the folder where the envelope lives.|
|folderUri|Path to the folder|
|ownerName|Name of the envelope owner|
|recipients|Recipient information and statuses listed by recipient types. This is the same as the information returned by the Get Envelope Recipient Status request.|
|recipientUri|Uri path of the envelope recipients.|
|senderName|Name of the envelope sender.|
|sentDateTime|Date/Time the envelope was sent.|
|status|Current status of the envelope|
|subject|Subject of the envelope.|

The following example shows the response json body.

### Example Response Body

    {
      "endPosition": "2",
      "folderItems": [{
        "createdDateTime": "2012-07-13T15:57:00.6900000Z",
        "envelopeId": "463d30c4-3z29-417b-9789-010d221a76b7",
        "envelopeUri": "\/envelopes\/463d30c4-3e29-417b-9789-010d221a76b7",
        "expireDateTime": "2012-11-10T21:21:05.2649771Z",
        "folderID": "237f9912-b96b-4d96-8adb-05523d497225",
        "folderUri": "\/folders\/237f9912-b96b-4d96-8adb-05523d497225",
        "ownerName": "Bill Cat",
        "recipients": {
          "signers": [{
            "email": "rc.cat@yahoo.com",
            "name": "Rod Cat",
            "routingOrder": 1,
            "status": "sent"
          },
          {
            "email": "dccat@gmail.com",
            "name": "Don Cat",
            "routingOrder": 1,
            "status": "sent"
         }]
        },
        "senderName": "Bill Cat",
        "sentDateTime": "2012-07-13T15:57:27.8670000Z",
        "status": "sent",
        "subject": "Please DocuSign this document: Agreement.pdf"
      }],
      "nextUri": "accounts/{accountId}/search_folders/{search_name}?start_position=3 "
      "previousUri": "accounts/{accountId}/search_folders/{search_name}?start_position=1 "
      "resultSetSize": "1",
      "startPosition": "2",
      "totalRows": "3"}
    }
