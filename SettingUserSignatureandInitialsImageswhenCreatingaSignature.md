# Setting User Signature and Initials Images when Creating a Signature

This allows user signature and/or initials images to be set when a signature is created. The rules and processes associated with this are:

<ul>
<li>If Content-Type is set to application/json, then default behavior for creating a default signature image, based on the name and a DocuSign font, is used.</li>
<li>If Content-Type is set to multipart/form-data, then the request must contain a first part with the user signature information, followed by parts that contain the images.</li>
<br/>
For each Image part, the Content-Disposition header has a “filename” value that is used to map to the “signatureName” and/or “signatureInitials” in the JSON to the image. For example: Content-Disposition: file; filename="Ron Test20121127083900"
<br/>
If no matching image (by filename value) is found then the image is not set. One, both or neither of the signature and initials images can be set with this call.
<br/>
The Content-Transfer-Encoding: base64 header, set in the header for the part containing the image, can be set to indicate that the images are formatted as base64 instead of as binary.
<br/>
<li>If successful, 200-OK is returned, and a JSON structure containing the signature information is provided, note that the signatureId can change with each API POST, PUT or DELETE since the changes to the signature structure cause the current signature to be closed, and a new signature record to be created.</li>
</ul>

## URL

    /accounts/{accountId}/users/{userId}/signatures

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account.

## HTTP Method

    POST

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|signatureFont|No|String|The font type for the signature, if the signature is not drawn. The supported font types are:<br/>"7_DocuSign", "1_DocuSign", "6_DocuSign", "8_DocuSign", "3_DocuSign", "Mistral", "4_DocuSign", "2_DocuSign", "5_DocuSign", "Rage Italic"|
|signatureInitials|No|String|The initials associated with the signature.|
|signatureName|Yes|String|The signature’s name in the system.|

## Request

### Example Request Body

The first example shows the default behavior and the second example shows a multipart request.
<br/><br/>

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/signatures
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "userSignatures": [{
        "signatureFont": "7_DocuSign",
        "signatureInitials": "R T20121127083847",
        "signatureName": "Ron Test20121127083847",
      }]
    }

<br/>

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/signatures
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: multipart/form-data; boundary=AAA
    
    -AAA
    Content-Type: application/json
    Content-Disposition: form-data
    
    {
      "userSignatures":[{
        "signatureFont":"7_DocuSign",
        "signatureInitials":"R T20121127083900",
        "signatureName":"Ron Test20121127083900"
      ]}
    }
    
    -AAA
    Content-Type: image/gif
    Content-Disposition: file;filename="Ron Test20121127083900"
    Content-Transer-Encoding: base64
    <base64 image bytes omitted>
    
    -AAA
    Content-Type: image/gif
    Content-Disposition: file;filename="R T20121127083900"
    Content-Transer-Encoding: base64
    <base64 image bytes omitted>
    -AAA

## Response

The response returns a success or failure and signature information.

### Example Response Body

    {
      "userSignatures":[{
        "adoptedDateTime":"String content",
        "createdDateTime":"String content",
        "initials150ImageId":"String content",
        "initialsImageUri":"String content",
        "signature150ImageId":"String content",
        "signatureFont":"String content",
        "signatureId":"String content",
        "signatureImageUri":"String content",
        "signatureInitials":"String content",
        "signatureName":"String content",
        "signatureType":"String content"
      }]
     }
