# Get User Account Settings

This returns the account settings list and email notification information for the specified user.

## URL

    /accounts/{accountId}/users/{userId}/settings

## HTTP Method

    GET

## Parameters

No additional parameters are required.

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>

## Response

The response returns the account setting name/value information and the email notification settings for the specified user. See the userSettings list for more information about the different user settings.

The following example shows the response json body.

### Example Response Body

    {
      "userSettings": [
        {
          "name": "sting",
          "value": "string",
        }
      ],
      "signerEmailNotifications": {
        "envelopeActivation": " string ",
        "envelopeComplete": " string",
        "carbonCopyNotification": "string",
        "certifiedDeliveryNotification": "string",
        "envelopeDeclined": "string",
        "envelopeVoided": "string",
        "envelopeCorrected": "string",
        "reassignedSigner": "string",
        "purgeDocuments": "string",
        "faxReceived": "string",
        "documentMarkupActivation": "string",
        "agentNotification": "string"
      },
      "senderEmailNotifications": {
        "envelopeComplete": "string",
        "changedSigner": "string",
        "senderEnvelopeDeclined": "string",
        "withdrawnConsent": "string",
        "recipientViewed": "string",
        "deliveryFailed": "string"
      }
    }
 
