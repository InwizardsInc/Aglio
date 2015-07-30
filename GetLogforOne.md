# Get a Connect Failure Log Entry

This is used to retrieve the Connect Failure Log information for one entry.

## URL

    /accounts/{accountId}/connect/failures/{failureId}

## HTTP Method

    GET

## Parameters

    There are no required parameters.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect/failures/{failureId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the Connect failure log information for the failure ID.

|Name|Type|Description|
|----|----|-----------|
|accountId|String|The account ID associated with the envelope.|
|configUrl|String|The web address of the listener or Retrieving Service end point for Connect.|
|connectId|String|The identifier for the Connect configuration that failed. If an account has multiple Connect configurations, this value is used to look up the Connect configuration for the failed post.|
|created|String|The date and time the entry was created.|
|email|String|The email that sent the envelope.|
|envelopeId|String|The envelope ID of the envelope status that failed to post.|
|error|String|The error that caused the Connect post to fail.|
|failureId|String|The failure log ID for the failure.|
|failureUri|String|The uri for the failure.|
|lastTry|String|The date and time the last attempt to post.|
|logId|String|The date and time the last attempt to post.|
|retryCount|Integer|The number of times the Connect post has been retried.|
|retryUri|String|The uri to retry to publish the Connect failure.|
|status|String|The new envelope status for the failed Connect post. The possible values are: Any, Voided, Created, Deleted, Sent, Delivered, Signed, Completed, Declined, TimedOut, Template, or Processing.|
|subject|String|The envelope subject.|
|userName|String|The name of the envelope sender.|

The following example shows the response json body.

    {
      "accountId":"String content",
      "configUrl":"String content",
      "connectId":"String content",
      "created":"String content",
      "email":"String content",
      "envelopeId":"String content",
      "error":"String content",
      "failureId":"String content",
      "failureUri":"String content",
      "lastTry":"String content",
      "logId":"String content",
      "logUri":"String content",
      "retryCount":"String content",
      "retryUri":"String content",
      "status":"String content",
      "subject":"String content",
      "userName":"String content"
    }
