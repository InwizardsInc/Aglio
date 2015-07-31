# Get the Connect Log

This retrieves a list of connect log entries for your account.

>**Note:** The enableLog setting in the Connect configuration must be set to true to enable logging.
> If logging is not enabled, then no log entries are recorded.

## URL

    /accounts/{accountId}/connect/logs

## HTTP Method

    GET

## Parameters

    There are no required parameters.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/connect/logs
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the Connect log information. The response is divided into two sections,
one for regular logs and one for Connect failures.

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
|lastTry|string|The date and time the last attempt to post.|
|logId|String|The Connect log ID for the entry.|
|LogUri|string|The uri for the log item.|
|retryCount|Integer|The number of times the Connect post has been retried.|
|retryUri|String|The uri to retry to publish the Connect failure.|
|status|String|The new envelope status for the failed Connect post. The possible values are: Any, Voided, Created, Deleted, Sent, Delivered, Signed, Completed, Declined, TimedOut, Template, or Processing.|
|subject|String|The envelope subject.|
|userName|String|The name of the envelope sender.|


The following example shows the response json body.

### Example Response Body

    {
      "type": "string",
      "logs": [
        {
          "accountId": "string",
          "envelopeId": "string",
          "subject": "string",
          "created": "string",
          "userName": "string",
          "email": "string",
          "status": "string",
          "lastTry": "string",
          "retryCount": "string",
          "error": "string",
          "connectId": "string",
          "configUrl": "string",
          "logUri": "string",
          "logId": "string",
          "failureUri": "string",
          "failureId": "string",
          "retryUri": "string",
        }
      ],
      "failures": [
        {
          "accountId": "string",
         "envelopeId": "string",
          "subject": "string",
          "created": "string",
          "userName": "string",
          "email": "string",
          "status": "string",
          "lastTry": "string",
          "retryCount": "string",
          "error": "string",
          "connectId": "string",
          "configUrl": "string",
          "logUri": "string",
          "logId": "string",
          "failureUri": "string",
          "failureId": "string",
          "retryUri": "string",
        }
      ],
      "totalRecords": "string"
    }
