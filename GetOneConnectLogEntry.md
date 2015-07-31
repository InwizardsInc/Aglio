# Get One Connect Log Entry

This retrieves one Connect log entry for your account.

>**Note:** The enableLog setting in the Connect configuration must be set to true to enable logging.
> If logging is not enabled, then no log entries are recorded.

## URL

    /accounts/{accountId}/connect/logs/{logId}
    Optional query string: additional_info=true

## HTTP Method

    GET

## Parameters

There are no required parameters, but the following optional query can be added to provide additional information in the response.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|additional_info|No|Boolean|When true, the connectDebugLog information is included in the response.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect/logs/{logId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the Connect log information for the requested log ID.

|Name|Type|Description|
|----|----|-----------|
|accountId|String|The account ID associated with the envelope.|
|configUrl|String|The web address of the listener or Retrieving Service end point for Connect.|
|connectId|String|The identifier for the Connect configuration that failed. If an account has multiple Connect configurations, this value is used to look up the Connect configuration for the failed post.|
|connectDebugLog||A complex element containing information about the Connect configuration, error details, date/time, description and payload.<br/><br/>This is only included in the response if the query additional_info=true is used.|
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
|retryUri|String|The uri to retry to publish the Connect failure.|
|status|String|The new envelope status for the failed Connect post. The possible values are: Any, Voided, Created, Deleted, Sent, Delivered, Signed, Completed, Declined, TimedOut, Template, or Processing.|
|subject|String|The envelope subject.|
|userName|String|The name of the envelope sender.|


The following example shows the response json body.

### Example Response Body

    {
      "accountId":"String content",
      "configUrl":"String content",
      "connectId":"String content",
      "connectDebugLog": [
        {
          "eventDateTime": "string",
          "connectConfig": "string",
          "eventDescription": "string",
          "payload": "string",
        }
      ],
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
