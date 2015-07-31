# Using Bulk Send in the REST API

With the Bulk Send feature, you can easily send the same document to a large number of recipients.
You just create a file that contains the list of recipient names and email addresses, start an envelope,
select your documents, add the bulk recipient file you created as a recipient, and send the envelope.
Once you send an envelope with a bulk recipient file, DocuSign creates a separate envelope for each
recipient in the bulk recipient file – eliminating the need to separately create and send an envelope for each signer.

Additionally, you can customize authentication (access code, ID check, phone authentication
or social network IDs), add notes and other custom information for each recipient in the list
by adding the information to the file.

### Bulk Send Limitations:

<ul><li>Bulk send must be enabled for your account (accountSettings enableBulkRecipient=true) and for the user sending the envelopes (userSettings allowBulkRecipients=true).</li><li>Bulk send can only be used with Signer recipient types and there can only be one bulk recipient in an envelope or template. An envelope or template can have other Signers and recipient types that are added to the envelope or template normally. When a bulk recipient file is added to an envelope, the single bulk recipient Signer is replaced with all recipients in the bulk recipient file. There can only be one bulk recipient file associated with an envelope when it is sent.</li><li>When an envelope with bulk recipients is sent, the envelopes are added to a bulk recipient queue and sent in a metered fashion. There is a limit of 2,000 envelopes in the bulk recipient queue and an error message is shown to the sender if this limit is reached. If you receive this error, you should wait and resend the envelope at a later time.</li></ul>

> **Note:** If you frequently run into queue limits, please contact your account manage to discuss modifying the queue limits for your account.

### General steps to use Bulk Send:

<ul><li>Create the bulk recipient CSV (Comma Separated Value) file.<br/>The required and optional information that can be included the file is described in the Add or Replace an Envelope Bulk Recipient File topic</li><li>Create draft envelope with a bulk recipient signer. The envelope can be created from a template that has a bulk recipient.<br/>A bulk recipient signer is a Signer recipient type where “isBulkRecipient” is set to true. (Note there can only be one bulk recipient signer per envelope).<br/>Templates and draft envelopes can be saved with a bulk recipient signer, but a bulk recipient file must be uploaded before an envelope with a bulk recipient signer can be sent.</li><li>Add (PUT) the bulk recipient file to the envelope.</li><li>Send the draft envelope.<br/>Transitioning an envelope with a bulk recipient signer from “created” to “sent” triggers the sending of an envelope for each recipient in the associated bulk recipient file. The original (draft) envelope is discarded. The response returned from sending the envelope included:<br/><ul><li>bulkRecipientsBatchId: This is the batch identifier used to query the status of the entire bulk send operation.</li><li>bulkRecipientTransactions: This is an array with identifying information about each envelope sent. The information included in this response:<ul><li>transactionId: The ID used to reference the queued envelope transaction.</li><li>name: The name of the recipient assigned to this envelope transaction.</li><li>email: The email address of the recipient assigned to this envelope transaction.</li></ul></li></ul></li></ul>
