# Add or Replace a Template Bulk Recipient File

This adds or replaces a bulk recipient file to a template. The Content-Type supported for uploading a bulk recipient file is CSV (text/csv).

The REST API does not support modifying individual rows or values in the bulk recipients file. It only allows the entire file to be added or replaced with a new file.

## URL

    /accounts/{accountId}/templates/{templateId}/recipients/{recipientId}/bulk_recipients

## HTTP Method

    PUT

## Parameters

The only required parameters are the template ID and recipient ID.

The parameters listed below are the supported fields for the csv file being added to the envelope.
The first row of the csv file is the header row that must have the field names for the file. Each subsequent
row represents a unique recipient with the information for that recipient.

There can be a maximum of 1,000 rows in the bulk recipient csv file.

If the value you are adding has a comma or double-quotation marks (“),
the value must be enclosed in double-quotation marks (“). Example: if you
have a Text tab with a tabLabel of Group and one of the entries for a recipient
is Inside Sales, NE, the would use “Inside Sales, NE” in the Group column for that recipient.

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|Name|Yes|String|The recipient’s name. This can be a maximum of 50 characters.|
|Email|Yes|String|The recipient’s email address. This can be a maximum of 100 characters.|
|Note|No|String|A note that will be unique to this recipient. This note will be sent to the recipient via the signing email. This note will also display in the signing UI. This can be a maximum of 1000 characters.|
|AccessCode|No|String|If a value is provided, the recipient must enter the value as the access code to view and sign the envelope. This can be a maximum of 50 characters and must conform to account’s access code format setting.<br/>If blank, but the signer accessCode is specified in the envelope, then that value is used.<br/>If blank and the signer accessCode is not specified, then access code is not required.|
|Identification|No|String|Specifies the authentication check used for the signer. If blank then no authentication check is required for the signer. Only one value can be used in this field.<br/>The acceptable values are:<br/><ul><li>KBA: Enables the normal ID check authentication set up for your account.</li><li>Phone: Enables phone authentication.</li><li>SMS: enables SMS authentication.</li></ul>|
|PhoneNumber|No|String|This is only used if the Identification field has Phone or SMS. The value for this field can be a valid telephone number or, if Phone, usersupplied (SMS authentication cannot use a user supplied number). Parenthesis and dashes can be used in the telephone number.<br/>If “usersupplied” is used, the signer supplies his or her own telephone number.|
|{tabLabel}|No|String|This is used to populate recipient tabs with information. This allows each bulk recipient signer to have different values for their associated tabs. Any number of tabLabel columns can be added to the bulk recipient file.<br/>The information used in the bulk recipient file header must be the same as the tabLabel for the tab.<br/>The values entered in this column are automatically inserted into the corresponding tab for the recipient in the same row.<br/>Note that this option cannot be used for tabs that do not have data or that are automatically populated data such as Signature, Full Name, Email Address, Company, Title, and Date Signed tabs.|

### Example Bulk Recipient CSV File

    Name,Email,Note,AccessCode,Identification,PhoneNumber,address1
    David Jones,david.jones@yahoo.com,Here is the document we discussed.,,ID Check,,123 Main St
    Kevin Smith,kevinmith@yahoo.com,,2243,,,697 My Way
    Elisabeth Bozick,elisabeth.bozick@yahoo.com,,,phone,usersupplied,827 1st Ave

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}//accounts/{accountId}/templates/
    {templateId}/recipients/{recipientId}/bulk_recipients
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Content-Type: application/json
    Content-Disposition: file;filename={file name};fileExtension=.csv

## Response

The response returns the recipient information for each row of the bulk recipient csv file, the total number of recipients in the file, and the bulkRecipientUri.

### Example Response

    {
      "bulkRecipients": [
        {
          "rowNumber": "string",
          "email": "string",
          "name": "string",
          "note": "string",
          "accessCode": "string",
          "identification": "string",
          "phoneNumber": "string",
          "tabLabels": [
            {
              "name": "string,"
              "value": "string"
            }
          ]
        },
        {
          "rowNumber": "string",
          "email": "string",
          "name": "string",
          "note": "string",
          "accessCode": "string",
          "identification": "string",
          "phoneNumber": "string",
          "tabLabels": [
            {
              "name": "string,"
              "value": "string"
            }
          ]
        }
      ],
      "bulkRecipientsCount": "string",
      "bulkRecipientsUri": "string"
    }
