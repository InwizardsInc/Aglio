# Add Recipients to an Envelope

This is used to add one or more recipients to an envelope.

>**Note:** For “In Process” envelopes (one that has been sent and is not completed or voided),
an email will be sent to a new recipient when they are reached in the routing order.
If the new recipient’s routing order is before or the same as the envelope’s next recipient,
an email is only sent if the optional “resend_envelope” query string is set to true.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients
    Optional query string: resend_envelope={true or false}

## HTTP Method

    POST

## Parameters

The parameters used to add recipients are the same as those used in an envelope. See the [Recipient Types and Parameters](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Recipient%20Parameter.htm) for more information.

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/recipients
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
     "signers":[{
        "accessCode":"String content",
        "addAccessCodeToEmail":"String content",
        "clientUserId":"String content",
        "customFields":["String content"],
        "emailNotification":{
          "emailBody":"String content",
          "emailSubject":"String content",
          "supportedLanguage":"String content"
        },
        "idCheckConfigurationName":"String content",
        "inheritEmailNotificationConfiguration":"String content",
        "note":"String content",
        "phoneAuthentication":{
          "recipMayProvideNumber":"String content",
          "recordVoicePrint":"String content",
          "senderProvidedNumbers":["String content"],
          "validateRecipProvidedNumber":"String content"
        },
        "recipientAttachments":[{
          "attachmentType":"String content",
          "label":"String content"
        }],
        "recipientId":"String content",
        "requireIdLookup":"String content",
        "roleName":"String content",
        "routingOrder":"String content",
        "socialAuthentications":[{
          "authentication":"String content"
        }],
       "email":"String content",
        "name":"String content",
        "defaultRecipient":"String content",
        "signInEachLocation":"String content",
        "signatureInfo":{
          "fontStyle":"String content",
          "signatureInitials":"String content",
          "signatureName":"String content"
       }
      }]
    }
    }

## Response

The response returns if the API execution is successful (200 – OK) or failed.
The response contains a recipient structure similar to that input.
If an error occurred during the POST operation for any of the recipients,
that recipient will contain an error node with an errorCode and message.

The following example shows the response json body.

### Example Response Body

    {
      "agents":[{
      }]
      "carbonCopies":[{
      }]
      "certifiedDeliveries":[{
      }]
      "editors":[{
      }]
      "agents":[{
      }]
     "inPersonSigners":[{
        "accessCode":"String content",
        "note":"String content",
        "recipientId":"String content",
        "requireIdLookup":"String content",
        "roleName":"String content",
        "routingOrder":"String content",
        "signerName":"String content",
        "status":"Created",
        "email":"String content",
        "name":"String content"
      }]
      "intermediaries":[{
      }]
      "signers":[{
        " accessCode":"String content",
        "note":"String content",
        "recipientId":"String content",
        "requireIdLookup":"String content",
        "roleName":"String content",
        "routingOrder":"String content",
        "status":"Created",
        "email":"String content",
        "name":"String content"
      }]
    }
