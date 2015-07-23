# Get Account Information

This returns the account information for the specified account.

## URL:

    /accounts/{accountId}/

## Formats: 

    XML, JSON

## HTTP Method:

    GET

## Parametrs:

    No parameters are required, only the specified account ID.

#### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}

## Response

The response returns the requested account information.

The canUpgrade information is true/false setting that shows if the account can be
upgraded through the API. The canCancelRenewal is true/false setting that shows
if the account can cancel automatic renewals.

The following example shows the response json body.

#### Example Response Body

    {
       "accountName":"String content",
       "billingPeriodEndDate":"String content",
       "billingPeriodEnvelopesAllowed":"String content",
       "billingPeriodEnvelopesSent":"String content",
       "billingPeriodStartDate":"String content",
       "canUpgrade": "String content",
       "canCancelRenewal": "String content",
       "connectPermission":"String content",
       "currentPlanId":"String content",
       "distributorCode":"String content",
       "docuSignLandingUrl":"String content",
       "forgottenPasswordQuestionCount":"String content",
       "planEndDate":"String content",
       "planName":"String content",
       "planStartDate":"String content",
       "suspensionDate":"String content",
       "suspensionStatus":"String content"
    }


