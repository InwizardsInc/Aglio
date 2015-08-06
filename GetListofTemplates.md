# Get List of Templates

Retrieves the list of templates for the specified account. The request can be limited to a specific folder.

## URL

    /accounts/{accountId}/templates
    Optional query strings: folder={string}, folder_ids={GUID, GUID},
    include={string}, count={integer}, start_position={integer},
    from_date={date/time}, to_date={date/time}, used_from_date={date/time},
    used_to_date={date/time}, search_text={string}, order={string}, order_by={string},
    user_filter={string}, shared_by_me={true/false}

## HTTP Method

    GET

## Parameters

The only information needed for this is the account ID, but the following optional queries can be added to the request.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|folder|No|String|The query value can be a folder name or folder ID. The response will only return templates in the specified folder.|
|folder_ids|No||A comma separated list of folder ID GUIDs.|
|include|No|String|A comma separated list of additional template attributes to include in the response. Valid values are: recipients, folders, documents, custom_fields, and notifications.|
|count|No|Integer|Number of records to return in the cache.|
|start_position|No|Integer|The starting index for the first template shown in the response. This must be greater than or equal to 0 (zero).|
|from_date|No|Date\Time|Start of the search date range. Only returns templates created on or after this date/time. If no value is specified, there is no limit on the earliest date created.|
|to_date|No|Date\Time|End of the search date range. Only returns templates created up to this date/time. If no value is provided, this defaults to the current date.|
|used_from_date|No|Date\Time|Start of the search date range. Only returns templates used or edited on or after this date/time. If no value is specified, there is no limit on the earliest date used.|
|used_to_date|No|Date\Time|End of the search date range. Only returns templates used or edited up to this date/time. If no value is provided, this defaults to the current date.|
|search_text|No|String|The search text used to search the names of templates.|
|order|No|String|Sets the direction order used to sort the list. Valid values are:<ul><li>asc = ascending sort order (a to z)</li><li>desc = descending sort order (z to a)</li></ul>|
|order_by|No|String|Sets the file attribute used to sort the list. Valid values are:<br/><ul><li>name – template name</li><li>modified – date/time template was last modified.</li><li>used – date/time the template was last used.</li></ul>|
|user_filter|No|String|Sets if the templates shown in the response Valid values are:<br/><ul><li>owned_by_me – only shows templates the user owns.</li><li>shared_with_me – only shows templates that are shared with the user.</li><li>all – shows all templates owned or shared with the user.</li></ul>|
|shared_by_me|No|Boolean|If true, the response only includes templates shared by the user. If false, the response only returns template not shared by the user. If not specified, the response is not affected.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/templates
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

This returns a list of templates for the account with the following information. If the optional folder query is used, only the templates in the specified folder are returned.

|Name|Description|
|----|-----------|
|resultSetSize|The number of results returned in this response.|
|startPosition|The index of the first element in the response set.|
|endPosition|The index of the last element in the response set.|
|totalSetSize|The total number of results from the call. This will always be greater than or equal to resultSetSize.|
|nextUri|Provides the Uri to the next chunk of records based on the search request. If the endPosition is the entire results of the search, this is null.|
|previousUri|Provides the Uri to the previous chunk of records based on the search request. If this response is the first response for the search, this is null.|
|folders|Folder information for the requested templates.|
|envelopeTemplates|The list of requested templates.|

The following example shows the response json body.

### Example Response Body

    {
      "resultSetSize": "string",
      "startPosition": "string",
      "endPosition": "string",
      "totalSetSize": "string",
      "nextUri": "string",
      "previousUri": "string",
      "folders": [
        {
          Note: folder definition omitted for brevity
        }
      ],
      "envelopeTemplates": [
        {
         Note: template definition omitted for brevity
        }
      ]
    }
