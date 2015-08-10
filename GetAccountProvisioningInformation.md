# Get Account Provisioning Information

This returns the account provisioning information.

## URL

    /accounts/provisioning

## HTTP Method

    GET

## Parameters

This request requires a DocuSign Integrator Key and the DocuSign AppToken information. The AppToken is used to determine the account provisioning information that is returned and is provided by the group provisioning the account.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/provisioning
    
    X-DocuSign-Authentication: <DocuSignCredentials><IntegratorKey>
                               {integrator_key}</IntegratorKey>
                               </DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json
    X-DocuSign-AppToken: {AppToken}

## Response

The response returns the account provisioning information.

The following example shows the response json body.

### Example Response Body

    {
      "distributorCode":"String content",
      "distributorPassword":"String content",
      "defaultPlanId":"String content",
      "defaultConnectionId":"String content",
      "planPromotionText":"String content",
      "passwordRuleText":"String content",
      "purchaseOrderOrPromAllowed":"String content"
    }
