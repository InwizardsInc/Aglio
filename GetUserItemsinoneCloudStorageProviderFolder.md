# Get User Items in one Cloud Storage Provider Folder

This retrieves a list of all items in one folder for the user from the selected cloud storage provider.

## URL

    /accounts/{accountId}/users/{userId}/cloud_storage/{serviceId}/folders/{folderId}
    Optional query parameters: start_position={integer}, count={integer},
    order={asc/desc}, order_by={modified/name}

## HTTP Method

    GET

## Parameters

There are no required parameters, but the following optional query parameter can be added to the request.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|start_position|No|String|An optional value that indicates the starting point of the first item included in the response set. It uses a 0-based index. The default setting for this is 0.|
|count|No|String|An optional value that sets how many items are included in the response.<br/>The default setting for this is 25.|
|order|No|String|An optional value that sets the direction order used to sort the item list. Valid values are:<ul><li>asc = ascending sort order</li><li>desc = descending sort order</li></ul>|
|order_by|No|String|An optional value that sets the file attribute used to sort the item list. Valid values are:<ul><li>modified</li><li>name</li></ul>|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountid}/users/
    {userid}/cloud_storage/{serviceid}/folders/{folderId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of all items in all folders with the selected cloud storage provider.

|Value|Description|
|-----|-----------|
|name|The name of the searched location.|
|id|The cloud storage provider ID for the searched location.|
|totalSetSize|The total number of items in the searched location.|
|resultSetSize|The number of items returned in the current request.|
|startPosition|The starting position of the current result set.|
|endPosition|The end position of the current result set.|
|items|This is a list of the items in the searched location. The list can include the following information:<br/><br/>**Note:** The information presented depends on the item type. Additionally, some cloud storage providers do not provide all the information.<ul><li>name: The name of the item.</li><li>id: The cloud storage provider ID for the item. This is the information used as the remoteUrl when trying to add the file as a document to an envelope.</li><li>date: The date the item was last modified.</li><li>type: Shows if the item is a file or a folder.</li><li>uri: The uri for the item.</li><li>size: The size (in bytes) of the item.</li><li>supported: A true or false value. When false the file type is included in the list of unsupported file types and cannot be included in a DocuSign envelope. When true, the file type is not included in the list of unsupported file types and might be able to be included in a DocuSign envelope.</li></ul>|

The following example shows the response json body.

### Example Response Body

    {
      "name": "My Folder",
      "id": "myfolder",
      "totalSetSize": "1",
      "resultSetSize": "1",
      "startPosition": "0",
      "endPosition": "0",
      "items": [
        {
          "name": "parking.pdf",
          "id": "1911:26490ea3-f725-4cb1-8e86-8275d93a1712:parking.pdf",
          "date": "2014-03-12T08:32:00.0000000Z",
          "type": "file",
          "size": "233400",
          "supported": "true"
        }
      ]
    }
