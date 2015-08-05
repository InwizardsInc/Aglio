# Get Account Settings

This returns the account settings information for the specified account.

## URL

    /accounts/{accountId}/settings

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the account setting name/value information for the specified account. See the [accountSettings list](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Create%20Account.htm#accountS) for more information about the different account settings.

The following example shows the response json body.

### Example Response Body

    {
      "accountSettings":[{
        "name":"String content",
        "value":"String content"
      }]
    }
