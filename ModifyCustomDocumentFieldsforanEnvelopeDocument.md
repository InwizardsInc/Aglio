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
