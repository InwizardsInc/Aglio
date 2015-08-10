# Modify User Account Settings

This updates the account settings list and email notifications for the specified user.

## URL

    /accounts/{accountId}/users/{userId}/settings

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|userSettings|No||The name/value pair information for user settings. These determine the actions that a user can take in the account. See the userSettings for more information about user settings.|
|signerEmailNotifications|No||An array of email notifications that sets the email the user receives when they are a signer. When the specific email notification is set to true, the user will receive those types of email notifications from DocuSign. Note: The user inherits the default account signer email notification settings when the user is created. The email notifications are:<ul><li>envelopeActivation</li><li>envelopeComplete</li><li>carbonCopyNotification</li><li>certifiedDeliveryNotification</li><li>envelopeDeclined</li><li>envelopeVoided</li><li>envelopeCorrected</li><li>reassignedSigner</li><li>purgeDocuments</li><li>faxReceived</li><li>documentMarkupActivation</li><li>agentNotification</li></ul>|
|senderEmailNotifications|No||An array of email notifications that sets the email the user receives when they are a sender. When the specific email notification is set to true, the user will receive those types of email notifications from DocuSign. Note: The user inherits the default account sender email notification settings when the user is created. The email notifications are:<ul><li>envelopeComplete</li><li>changedSigner</li><li>senderEnvelopeDeclined</li><li>withdrawnConsent</li><li>recipientViewed</li><li>deliveryFailed</li></ul>|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/settings
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "userSettings": [
        {
          "name": "sting",
          "value": "string"
        },
        {
          "name": "string",
          "value": "string"
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

## Response

    The response returns success or failure.
