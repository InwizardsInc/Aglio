# Create Multiple Accounts

This is used to create multiple DocuSign accounts with one call. 
It uses the same information and formats as the normal Create Account 
call with the information included within a newAccountRequests element. 
A maximum of 100 new accounts can be created at one time.

## URL

    /accounts

## Formats

    XML, JSON

## HTTP Method
    POST

## Parameters

See the [Create Account](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Create%20Account.htm) parameters for the information needed for creating an account.

### Example JSON Request Body

    POST https://{server}/restapi/{apiVersion}/accounts/
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>
                               {integrator_key}</IntegratorKey></DocuSignCredentials>
    
    
    {
        "newAccountRequests": [
          {
            (Account details ommitted for brevity)
          },
          {
            (Account details ommitted for brevity)
          }
      ]
    }

### Example XML Request Body

Note that the structure of the XML request is slightly different than the json request, 
in that the new account information is included in a newAccountDefinition element inside 
the newAccountRequests element.

    <newAccountsDefinition xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://www.docusign.com/restapi">
      <newAccountRequests>
        <newAccountDefinition>
          (Account details ommitted for brevity)
        </newAccountDefinition>
      <newAccountDefinition>
      <newAccountRequests>
        (Account details ommitted for brevity)
      </newAccountRequests>
    </newAccountsDefinition>

## Response

The response returns the new account ID, password and the default user information for each newly created account.

> **Note:**  A 201 code is returned if the call succeeded, 
> but some of the individual account requests failed. 
> In this case an errorDetails node is added to the new account 
> element that failed to create a new account.

The following examples show the response json and xml bodies.

### Example JSON Response Body

    {
      "newAccounts": [
        {
          "accountId": "string",
          "userId": "string",
          "apiPassword": "string",
          "baseUrl": "string",
          "accountIdGuid": "string"
        },
        {
          "accountId": "string",
          "userId": "string",
          "apiPassword": "string",
          "baseUrl": "string",
          "accountIdGuid": "string"
        }
      ]
    }

### Example XML Response Body

    <newAccountsSummary xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://www.docusign.com/restapi">
      <newAccounts>
        <newAccountSummary>
          <accountId>string</accountId>
          <accountIdGuid>string</accountIdGuid>
          <apiPassword>string</apiPassword>
          <baseUrl>string</baseUrl>
          <userId>string</userId>
        </newAccountSummary>
        <newAccountSummary>
          <accountId>string</accountId>
          <accountIdGuid>string</accountIdGuid>
          <apiPassword>string</apiPassword>
          <baseUrl>string</baseUrl>
          <userId>string</userId>
        </newAccountSummary>
      </newAccounts>
    </newAccountsSummary>

