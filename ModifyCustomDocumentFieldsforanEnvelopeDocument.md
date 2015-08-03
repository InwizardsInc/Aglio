# Modify Custom Document Fields for an Envelope Document

This modifies existing custom document fields for an existing envelope document.

## URL

    /accounts/{accountId}/envelopes/{envelopeId}/documents/{documentId}/fields

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|documentFields|Yes|documentField|The array of name-value custom data strings to be added to a document. Custom document field information is returned in the status, but otherwise is not used by DocuSign. The array contains the elements:<br/>name – A string that can be a maximum of 50 characters.<br/>value – A string that can be a maximum of 200 characters.|<br/>**IMPORTTANT:** If using xml, the name/value pair is contained in a nameValue element.|

## Request

### Example JSON Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/envelopes/
    {envelopeId}/documents/{documentId}/fields
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    {
      "documentFields": [
        {
          "name": "sample string 1",
          "value": "sample string 2",
        },
        {
          "name": "sample string 1",
          "value": "sample string 2",
        }
      ]
    }

### Example XML Request Body

    <documentFieldsInformation xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://www.docusign.com/restapi">
      <documentFields>
       <nameValue>
          <name>sample string 1</name>
          <value>sample string 2</value>
        </nameValue>
        <nameValue>
          <name>sample string 1</name>
          <value>sample string 2</value>
        </nameValue>
      </documentFields>
    </documentFieldsInformation>

## Response

The response returns the modified custom document field name-value pairs
for the document and any errors associated with the fields.

Examples of the response body for json and XML are shown below.

### Example JSON Response Body

    {
      "documentFields": [
        {
          "name": "sample string",
          "value": "sample string",
          "errorDetails": {
          "errorCode": "sample string",
          "message": "sample string"
        }
        },
        {
          "name": "sample string",
          "value": "sample string",
          "errorDetails": {
          "errorCode": "sample string",
           "message": "sample string"
          }
        }
      ]
      }

### Example XML Response Body

Note that the structure of the XML response is slightly different
than the json response, in that the name/value pairs are included in a nameValue element.

    <documentFieldsInformation xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://www.docusign.com/restapi">
      <documentFields>
        <nameValue>
          <errorDetails>
            <errorCode>sample string</errorCode>
            <message>sample string</message>
          </errorDetails>
          <name>sample string</name>
          <value>sample string</value>
        </nameValue>
        <nameValue>
          <errorDetails>
            <errorCode>sample string</errorCode>
            <message>sample string</message>
         </errorDetails>
        <name>sample string</name>
        <value>sample string</value>
       </nameValue>
      </documentFields>
    </documentFieldsInformation>
