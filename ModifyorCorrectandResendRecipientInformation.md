# Modify or Correct and Resend Recipient Information

This lets you modify recipients in a draft envelope or correct recipient information for an in process envelope.

For draft envelopes, you can edit: email, userName, routingOrder, faxNumber, deliveryMethod, accessCode and requireIdLookup.

>**Note:** If you send information for a recipient that does not already exist in a draft envelope, the recipient will be added to the envelope (similar to the [POST](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Add%20Recipients%20to%20an%20Envelope.htm)).
Once an envelope has been sent, you can only edit: email, userName, signerName, routingOrder, faxNumber, and deliveryMethod. You can also select to resend an envelope by using the resend_envelope option.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/recipients
    Optional addition: resend_envelope {true or false}

## HTTP Method

    PUT

## Parameters

The parameters used to modify recipients are the same as those used in an envelope. See [the Recipient Types and Parameters](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Recipient%20Parameter.htm) for more information. The resend_envelope flag is only used to resend an In Process envelope.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|resend_envelope|No|String|True or false setting that defaults to false. Setting this to true will resend the envelope to the recipient.|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}/recipients
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "signers" :
      [
      {
        "email": "mike.roseleip@docusign.com",
        "name": "Mike Roseleip",
        "recipientId": "1"
      }
      ]
    }

## Response

The response returns if the correction was successful.

The following example shows the response json body.

### Example Response Body

    {
      "recipientUpdateResults": [{
        "errorDetails": {
          "errorCode": "SUCCESS",
          "message": ""
        },
      "recipientId": "1"
      }]
    }
