# Get Custom Document Fields for a Template Document

This returns the custom document fields for an existing document in a template.

## URL

    /accounts/{accountId}/templates/{templateId}/documents/{documentId}/fields

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/templates/{templateId}/documents/{documentId}/fields
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the custom document field name-value pairs for the requested document ID.

Examples of the response body for json and XML are shown below.

### Example JSON Response Body

    {
      "documentFields": [
        {
          "name": "sample string",
          "value": "sample string"
        },
        {
          "name": "sample string",
          "value": "sample string"
        }
      ]
    }

### Example XML Response Body

Note that the structure of the XML response is slightly different than the json response, in that the name/value pairs are included in a nameValue element.

    <documentFieldsInformation xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://www.docusign.com/restapi">
      <documentFields>
        <nameValue>
          <name>sample string</name>
          <value>sample string</value> 
        </nameValue>
        <nameValue>
          <name>sample string</name>
          <value>sample string</value>
        </nameValue>
      </documentFields>
    </documentFieldsInformation>
