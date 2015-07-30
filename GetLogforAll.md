# Get the Connect Failure Log

This is used to retrieve the Connect Failure Log information.
It can be used to determine which envelopes failed to post, so a republish request can be created.

## URL

    /accounts/{accountId}/connect/failures

## HTTP Method

    GET

## Parameters

    There are no required parameters.

## Request

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect/failures
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the Connect failures log and the total number of records in the log.

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
|logId|String|The Connect log ID for the entry.|
|LogUri|String|The uri for the log item.|
|retryCount|Integer|The number of times the Connect post has been retried.|
|status|String|The new envelope status for the failed Connect post. The possible values are: Any, Voided, Created, Deleted, Sent, Delivered, Signed, Completed, Declined, TimedOut, Template, or Processing.|
|subject|String|The envelope subject.|
|userName|String|The name of the envelope sender.|

The following example shows the response json body.

### Example Response Body

    {
      "failures":[{
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
      },
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
      "userName":"String content"}],
    }],
    "totalRecords":"String content",
    "type":"String content"
    }
