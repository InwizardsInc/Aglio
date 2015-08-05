# Get Folder List

Returns a list of the folders for the account, including the folder hierarchy.
There is an option to include the list of template folders and templates.

## URL

    /accounts/{accountId}/folders
    Optional query string: template={string}

## HTTP Method

    GET

## Parameters

No additional parameters are required, but the following optional parameter can be added to the request.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|template|No|String|The two possible values are “include” or “only.”<br/><ul><li>include - The folder list will return normal folders plus template folders.</li><li>only - Only the list of template folders are returned.</li></ul>|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/folders
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the list of folders for the account.
The folder list includes the folder ID, the folder name, the name,
user ID and email of the folder’s owner, the folder type and uri. If the
folder is a sub-folder of another folder, the parent folder information is returned.
If the template query is included, the template folder structure, along with the templates
within each folder, is also returned.

The following example shows the response json body. The last folder in the example is shows a sub-folder.

### Example Response Body

    {
      "folders": [
        {
          "ownerUserName": "String content",
          "ownerEmail": "String content",
          "ownerUserId": "String content",
          "type": "String content",
          "name": "String content",
          "uri": "String content",
          "parentFolderId": "String content",
          "parentFolderUri": "String content",
          "folderId": "String content",
          "filter": {
            "actionRequired": "String content",
            "expires": "String content",
            "isTemplate": "String content",
            "status": "String content",
            "fromDateTime": "String content",
            "toDateTime": "String content",
            "searchTarget": "String content",
            "searchText": "String content",
            "folderIds": "String content",
            "orderBy": "String content",
            "order": "String content"
          }
        },
      ]
    }
