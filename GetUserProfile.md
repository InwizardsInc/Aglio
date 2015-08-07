# Get User Profile

This returns user profile information, the privacy settings and personal information (address, phone number, etc.).

## URL

    /accounts/{accountId}/users/{userId}/profile

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account.

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/profile
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json

## Response

The response returns the user profile information from the user’s ID card. The User Profile contains the following information.

|Name|Description|
|----|-----------|
|address|The user’s address information. A complex element consisting of the optional elements: address1, address2, city, country, fax, phone, postalCode, stateOrProvince.|
|authenticationMethods|Shows the authentication methods used by the user.|
|companyName|The user’s Company information.|
|displayOrganizationInfo|When true, the user’s company and title information are shown on the ID card.|
|displayPersonalinfo|When true, the user’s Address and Phone number are shown on the ID card.|
|displayProfile|When true, the user’s ID card can be viewed from signed documents and envelope history.|
|displayUsageHistory|When true, the user’s usage information is shown on the ID card.|
|title|The user’s Title information.|
|usageHistory|A complex element consisting of:<ul><li>lastSentDateTime – the date and time the user last sent an envelope.</li><li>lastSignedDateTime – the date and time the user last signed an envelope.</li><li>sentCount – the number of envelopes the user has sent.</li><li>signedCount – the number of enevelopes the user has signed.</li></ul>|
|userDetails|A complex element with the user name information consisting of:<ul><li>firstName – The user’s first name.</li><li>lastName – The user’s last name.</li><li>middleName – The user’s middle name.</li><li>suffixName – The suffix for the user’s name.</li><li>title – The user’s title.</li></ul>|

The following example shows the response json body.

### Example Response Body

    {
      "address":{
        "address1":"String content",
        "address2":"String content",
        "city":"String content",
        "country":"String content",
        "fax":"String content",
        "phone":"String content",
        "postalCode":"String content",
        "stateOrProvince":"String content"
      },
      "authenticationMethods":[{
        "authenticationType":"String content",
        "lastProvider":"String content",
        "lastTimestamp":"String content",
        "totalCount":2147483647
      }],
      "companyName":"String content",
      "displayOrganizationInfo":"String content",
      "displayPersonalInfo":"String content",
      "displayProfile":"String content",
      "displayUsageHistory":"String content",
      "title":"String content",
      "usageHistory":{
        "lastSentDateTime":"String content",
        "lastSignedDateTime":"String content",
        "sentCount":2147483647,
        "signedCount":2147483647
      }
      "userDetails":{
        "firstName":"String content",
        "lastName":"String content",
        "middleName":"String content",
        "suffixName":"String content",
        "title":"String content",
      }
    }
