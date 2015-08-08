# Modify User Profile

This sets the user’s detail information, profile information, privacy settings and personal information in the user ID card.

This can also be used to change a user’s name by changing the information in the user details (userDetails). When changing a user’s name, you can either change the information in the userName OR change the information in firstName, middleName, lastName, suffixName and title. Changes to firstName, middleName, lastName, suffixName and title take precedence over changes to the userName.

## URL

    /accounts/{accountId}/users/{userId}/profile

>**Note:** The userId specified in the uri must match the authenticated user’s userId and the user must be a member of the account.

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|address|No|String|The user’s address information. A complex element consisting of the optional elements: address1, address2, city, country, fax, phone, postalCode, stateOrProvince.|
|authenticationMethods|No|authenticationMethods|These properties cannot be modified in the PUT.<br/>Shows the authentication methods used by the user. A complex element consisting of:<ul><li>authenticationMethodType (PhoneAuth, STAN, ISCheck, OFAC, AccessCode, AgeVerify, or SSOAuth)</li><li>lastTimestamp – the data and time the user last used the authentication method.</li><li>lastProvider – the last provider that authenticated the user.</li><li>totalCount – the number of times used.</li></ul>|
|companyName|No|String|The user’s Company information.|
|displayOrganizationInfo|No|String|True/False setting. When true, the user’s company and title information are shown on the ID card.|
|displayPersonalinfo|No|String|True/False setting. When true, the user’s Address and Phone number are shown on the ID card.|
|displayProfile|NO|string|True/False setting. When true, the user’s ID card can be viewed from signed documents and envelope history.|
|displayUsageHistory|No|String|True/False setting. When true, the user’s usage information is shown on the ID card.|
|title|No|String|The user’s Title information.|
|usageHistory|No|usageHistory|A complex element consisting of:<ul><li>lastSentDateTime – the date and time the user last sent an envelope.</li><li>lastSignedDateTime – the date and time the user last signed an envelope.</li><li>sentCount – the number of envelopes the user has sent.</li><li>signedCount – the number of envelopes the user has signed.</li></ul>|
|userDetails|No|userDetails|A complex element with the user name information consisting of:<ul><li>firstName – The user’s first name. This can be a maximum of 50 characters.</li><li>lastName – The user’s last name. This can be a maximum of 50 characters.</li><li>middleName – The user’s middle name. This can be a maximum of 50 characters.</li><li>suffixName – The suffix for the user’s name. This can be a maximum of 50 characters.</li><li>title – The user’s title. This can be a maximum of 10 characters.</li><li>username – The user’s full name. This can be a maximum of 100 characters.</li></ul>|

## Request

### Example Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountId}/users/{userId}/profile
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
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
      "userName":"String content"
    }
    }
