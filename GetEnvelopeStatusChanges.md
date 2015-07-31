# Get Envelope Status Changes

This returns envelope status changes for all envelopes. The information returned
can be modified by adding query strings to limit the request to check between
certain dates and times, or for certain envelopes, or for certain status codes.
It is recommended that you use one or more of the query strings in order to
limit the size of the response.

>**Important:** Unless you are requesting the status for specific envelopes
> (using envelopeIds or transactionIds), you must add a from_date in the request.
> 
> Getting envelope status using transactionIds is useful for offline signing
> situations where it can be used determine if an envelope was created or not,
> for the cases where a network connection was lost, before the envelope status could be returned.

### Request Envelope Status Notes

The REST API GET /envelopes call uses certain filters to find results. In some cases requests
are check for “any status change” instead of the just the single status requested. In these cases,
more envelopes might be returned by the request than otherwise would be. For example, for a request
with the begin date is set to Jan 1st, an end date set to Jan 7th and the status qualifier (from_to_status)
set to “Delivered” – the response set might contain envelopes that were created during that time period, but not
delivered during the time period.

To avoid unnecessary database queries, the DocuSign system checks requests to ensure that
the added filters will not result in a zero-size response before acting on the request. The
following table shows the valid envelope statuses (in the Valid Current Statuses column) for the
status qualifiers in the request. If the status and status qualifiers in the API request do not contain
any of the values shown in the valid current statuses column, then an empty list is returned.

For example, a request with a status qualifier (from_to_status) of “Delivered” and a status
of “Created,Sent”, DocuSign will always return an empty list. This is because the request essentially
translates to: find the envelopes that were Delivered between the begin and end dates that have a current
status of Created or Sent, and since an envelope that has been delivered can never have a status of Created
or Sent, a zero-size response would be generated. In this case, DocuSign does not run the request, but just returns
the empty list.

Client applications should check that the statuses they are requesting make sense for a given status qualifier.

|Status Qualifier<br/>(from_to_status)|Effective Status Qualifier|Valid Current Statuses|
|-------------------------------------|--------------------------|----------------------|
|Any (changed)|StatusChanged|Any, Created, Sent, Delivered, Signed, Completed, Declined, Voided, Deleted|
|Created|Created|Any, Created, Sent, Delivered, Signed, Completed, Declined, Voided, Deleted|
|Sent|Sent|Any, Sent, Delivered, Signed, Completed, Declined, Voided, Deleted|
|Delivered|StatusChanged|Any, Delivered, Signed, Completed, Declined, Voided, Deleted|
|Signed|StatusChanged|Any, Signed, Completed, Declined, Voided, Deleted|
|Completed|Completed|Any, Completed, Declined, Voided, Deleted|
|Declined|StatusChanged|Any, Declined, Voided, Deleted|
|TimedOut - Always return zero results|StatusChanged|Any, Voided, Deleted|
|Voided|Voided|Any, Voided, Deleted|
|Deleted|StatusChanged|Any, Deleted|

## URL

    /accounts/{accountId}/envelopes
    
    Optional query strings: from_date={dateTime}, to_date={dateTime}, status={status code},
    from_to_status={changed or any or list of statuses}, envelopeId={envelopeId},
    custom_field={envelope custom field name}={envelope custom field value},
    transaction_ids={transactionId or request_body}

## HTTP Method

    GET

## Parameters

There are no required parameters, but the following optional parameters can be added to narrow the search results.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|from_date|No*|dateTime|The date/time setting that specifies the date/time when the request begins checking for status changes for envelopes in the account.<br/><br/>* This is required unless envelopeIds are used.|
|to_date|No|dateTime|Optional date/time setting that specifies the date/time when the request stops for status changes for envelopes in the account. If no entry, the system uses the time of the call as the to_date.|
|from_to_status|No|EnvelopeStatusChange|This is the status type checked for in the from_date/to_date period. If "changed" is specified, then envelopes that changed status during the period are found. If for example, "created" is specified, then envelopes created during the period are found. Default is “changed”.<br/>Possible values are: Voided, Changed, Created, Deleted, Sent, Delivered, Signed, Completed, Declined, TimedOut and Processing.|
|status|No|String|The list of current statuses to include in the response. By default, all envelopes found are returned. If values are specified, then of the envelopes found, only those with the current status specified are returned in the results.<br/>Possible values are: Voided, Created, Deleted, Sent, Delivered, Signed, Completed, Declined, TimedOut and Processing.|
|ac_status|No|String|Specifies the Authoritative Copy Status for the envelopes. The possible values are: Unknown, Original, Transferred, AuthoritativeCopy, AuthoritativeCopyExportPending, AuthoritativeCopyExported, DepositPending, Deposited, DepositedEO, or DepositFailed.|
|envelopeId|No|String|The envelope ID for the envelope.|
|custom_field|No|String|This specifies the envelope custom field name and value searched for in the envelope information. The value portion of the query can use partial strings by adding ‘%’ (percent sign) around the custom field query value.<br/><br/>Example 1: If you have an envelope custom field called “Region” and you want to search for all envelopes where the value is “West” you would use the query: ?custom_field=Region=West.<br/><br/>Example 2: To search for envelopes where the ApplicationID custom field has the value or partial value of “DocuSign” in field, the query would be: ?custom_field=ApplicationId=%DocuSign% This would find envelopes where the custom field value is “DocuSign for Salesforce” or “DocuSign envelope.”|
|transactionId|No|String|If included in the query string, this is a comma separated list of envelope transactionIds.<br/>If included in the request_body, this is a list of envelope transactionIds.<br/>**Note:** transactionIds are only valid in the DocuSign system for 7 days.|

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>
                               {integrator_key}</IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the uri’s for the envelope certificate, custom fields, documents,
envelope along with the envelope ID, envelope status, and the date-time stamp for the
envelope status change for the envelopes. If a query string was added to the original request,
only the envelopes that meet those parameters are included in the response.

The following example shows the response json body.

### Example Request Body

    {
    {
      "envelopes": [{
        "certificateUri": "String content",
        "customFieldsUri": "String content",
        "documentsCombinedUri": "String content",
        "documentsUri": "String content",
        "envelopeId": "String content",
        "envelopeUri": "String content",
        "notificationUri": "String content",
        "recipientsUri": "String content",
        "status": "String content",
        "statusChangedDateTime": "String content"
      },
      {
        "certificateUri": "String content",
        "customFieldsUri": "String content",
        "documentsCombinedUri": "String content",
        "documentsUri": "String content",
        "envelopeId": "String content",
        "envelopeUri": "String content",
        "notificationUri": "String content",
        "recipientsUri": "String content",
        "status": "String content",
        "statusChangedDateTime": "String content"
      }],
    "resultSetSize": "String content"}
    }
