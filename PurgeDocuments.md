# Purge Documents

This provides the ability to initiate a request to place envelope documents
and envelope metadata in a purge queue so that this information is removed from
the DocuSign system. The request can only be used for completed envelopes that are
not marked as authoritative copy. The requesting user must have permission to purge documents
and must be the sender (the requesting user can act as the sender using Send On Behalf Of).

>**Note:** If your account has set up a Document Retention policy by specifying the number
> of days to retain documents, at the end of the retention period the envelope documents
> are automatically placed in the purge queue and the warning emails are sent. So setting
> a Document Retention policy is the same as setting a schedule for purging documents.
> The Document Retention policy is set in the Classic DocuSign Experience.

When the purge request is initiated the envelope documents, or documents and envelope metadata,
are placed in a purge queue for deletion in 14 days. A warning email notification is sent to the
sender and recipients associated with the envelope notifying them that the envelope documents will
be deleted in 14 days and providing a link to the documents. A second email is sent 7 days later with
the same message. At the end of the 14-day period, the envelope documents are deleted from the system.

If purgeState=”documents_queued” is used in the request, then only the documents are deleted and any
corresponding attachments and tabs remain in the DocuSign system. If purgeState= ”documents_and_metadata_queued”
is used in the request, then the documents, attachments, and tabs are deleted

## URL

    /accounts/{accountId}/envelopes/{envelopeId}

## HTTP Method

    PUT

## Parameters
|Name|Required?|Type|Description|
|----|---------|----|-----------|
|purgeState|Yes|String|Initiates a purge request. The accepted values are:<br/><ul><li>documents_queued: Places envelope documents in the purge queue.</li><li>documents_and_metadata_queued: Places envelope documents and metadata in the purge queue.</li></ul>|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/{envelopeId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "purgeState": "String"
    }

## Response

    The response returns success or failure of the operation.
