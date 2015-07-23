# Login

The /login_information API is used to determine if a user is authenticated 
and to choose the account to be used for other operations. 
Each account associated with the login credentials is listed. 
The “baseUrl” parameter is used in all future API calls as the base of the request URL. 
This baseUrl contains the DocuSign server, the API version, and the accountId to be used for the login.

This request uses your DocuSign credentials to retrieve the account information.

## URL:

    https://{server}/restapi/{apiVersion}/login_information
    
    Optional query strings: api_password={true or false}, include_account_id_guid={true or false}, 
    login_settings={all or none}

## HTTP Method:
    GET

## Parameters:

There are no required parameters, but the following optional query strings can be added to the request.

|Name              |Required?  |Type       |Description                                             |
|------------------|-----------|-----------|--------------------------------------------------------|
|api_password|No|Boolean|When set to true, shows the account API password in the response.|
|include_account_id_guid|No|Boolean|When set to true, shows the account ID GUID in the response.|
|login_setting|No|String|Can be set to all or none. when set to all, all the login settings are returned. when set to none, no login settings are returned.|

### Example Request Body

    GET https://{SERVER}/restapi/{apiVersion}/login_information
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>{password}
                               </Password><IntegratorKey>{integrator_key}</IntegratorKey>
                               </DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns account information for the account associated with your 
DocuSign credentials, along with any optional information included in the request. 
The baseUrl information for future calls is included in the response.

The following example shows the header followed by the response json body.

### Example Request Body

    200 OK
    Content-Length: 557
    Cache-Control: private
    Content-Type: application/json; charset=utf-8
    Date: Tue, 06 Mar 2012 17:22:07 GMT
    {
      "apiPassword":"String content",
      "loginAccounts": [{
         "accountId":"String content",
         "baseUrl":"String content",
         "email":"String content",
         "isDefault":"String content",
         "loginAccountSettings":[{
           "name":"String content",
           "value":"String content"
         }],
      "loginUserSettings":[{
        "name":"String content",
         "value":"String content"
      }],
      "name":"String content",
      "siteDescription":"String content",
      "userId":"String content",
      "userName":"String content"
    }
