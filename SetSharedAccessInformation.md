# Set Shared Access Information

This sets the shared access status for one or more users. Only users with account
administration privileges can set shared access status. Changes to the shared items
status are not additive; the change always replaces the current status.

## URL

    /accounts/{accountId}/shared_access

## HTTP Method

    PUT

## Parameters

|Name|Required?|Type|Description|
|----|---------|----|-----------|
|user|Yes|String||
|envelopes|Yes|String|The shared access information for envelopes<br/>user: The userId of the account user for whom the shared access status is being changed. The status change is relative to the user set by the userId described above.<br/>shared: Specifies the change to the sharing status between the user and account user for envelopes.<br/>The accepted values are:<br/><ul><li>not_shared: This removes all sharing between the user and the account user for envelopes.</li><li>shared_to: Returns account users that the specified item type is not being shared with and who are sharing the specified item type with the user (only shared to the user).</li><li>shared_from: Returns account users that the specified item type is being shared with and who are not sharing the specified item type with the user (only shared from the user).</li><li>shared_to_and_from: This shares access to and from envelopes for both the user and the account user.</li></ul>|

## Request

### Example JSON Request Body

    PUT https://{server}/restapi/{apiVersion}/accounts/{accountid}/shared_access
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                               {password}</Password><IntegratorKey>{integrator_key}
                               </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/json
    
    {
      "sharedAccess": [
        {
          "user": {
            "userId": "123",
          },
          “envelopes”: [
            {
              "user": {
                "userId": "1234",
              },
            "shared": "shared_to"
            },
            {
              "user": {
                "userId": "123456",
              },
              "shared": "shared_from"
            }
          ]
        },
        {
          "user": {
            "userId": "3770d021-0c10-4652-809b-01b669308bb8",
          },
          “envelopes”: [
            {
              "user": {
                "userId": "123",
              },
              "shared": "shared_to"
            }
          ]
        },
        {
          "user": {
            "userId": "98ca4b2c-c46f-4802-9bd6-06448cf2abbb",
          },
          “envelopes”: [
            {
              "user": {
                "userId": "3770d021-0c10-4652-809b-01b669308bb8",
              },
              "shared": "shared_to"
            },
            {
              "user": {
                "userId": "29c56d02-ec97-4a2a-b99d-6c5a2e400b8b",
              },
             "shared": "shared_to_and_from"
            }
          ]
        }
      ]
    }

### Example XML Request Body

Note that the structure of the XML request is slightly different than the json request, in that the user and envelopes information are included in the memberSharedItems element.

    <accountSharedAccess xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://www.docusign.com/restapi">
      <sharedAccess>
        <memberSharedItems>
          <envelopes>
            <sharedItem>
              <shared>string</shared>
              <user>
                <userId>string</userId>
              </user>
            </sharedItem>
            <sharedItem>
              <shared>string</shared>
              <user>
                <userId>string</userId>
              </user>
            </sharedItem>
          </envelopes>
          <user>
            <userId>string</userId>
          </user>
        </memberSharedItems>
        <memberSharedItems>
          <envelopes>
            <sharedItem>
          <shared>string</shared>
            <user>
                <userId>string</userId>
              </user>
            </sharedItem>
          </envelopes>
        </memberSharedItems>
      </sharedAccess>
      <startPosition>string</startPosition>
      <totalSetSize>string</totalSetSize>
    </accountSharedAccess>

## Response

The response returns a success or failure, along with the changed shared access status.

Examples of the response body for json and XML are shown below.

### Example JSON Response Body

    {
      "sharedAccess": [
        {
          "user": {
            "userId": "123",
         },
          "errorDetails": {
            "errorCode": "INVALID_USERID",
            "message": "Invalid Userid."
          }
        },
        {
          "user": {
            "userId": "3770d021-0c10-4652-809b-01b669308bb8",
          },
          "envelopes": [
            {
              "user": {
                "userId": "123",
              },
              "errorDetails": {
                "errorCode": "INVALID_USERID",
                "message": "Invalid Userid."
               }
            }
          ]
        },
        {
          "user": {
            "userName": "Estevan Doe",
            "userId": "98ca4b2c-c46f-4802-9bd6-06448cf2abbb ",
            "email": estevan.doe@docusign.com
          },
          "envelopes": [
            {
              "user": {
                "userName": "Jane Doe",
                "userId": "3770d021-0c10-4652-809b-01b669308bb8",
                "email": "jane.doe@docusign.com"
              },
              "shared": "shared_to"
            },
            {
              "user": {
                "userId": "29c56d02-ec97-4a2a-b99d-6c5a2e400b8b",
              },
              "errorDetails": {
                "errorCode": "USER_LACKS_MEMBERSHIP",
                "message": "The UserID does not have a valid membership in this Account."
               }
            }
          ]
        }
      ]

### Example XML Response Body

Note that the structure of the XML response is slightly different than the json response,
in that the user and envelopes information are included in the memberSharedItems element.

    <accountSharedAccess xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://www.docusign.com/restapi">
      <accountId>string</accountId>
      <endPosition>string</endPosition>
      <errorDetails>
        <errorCode>string</errorCode>
        <message>string</message>
      </errorDetails>
      <nextUri>string</nextUri>
      <previousUri>string</previousUri>
      <resultSetSize>string</resultSetSize>
      <sharedAccess>
        <memberSharedItems>
          <errorDetails>
            <errorCode>string</errorCode>
            <message>string</message>
          </errorDetails>
          <user>
            <email>string</email>
            <uri>string</uri>
            <userId>string</userId>
            <userName>string</userName>
          </user>
          <envelopes>
        <sharedItem>
          <errorDetails>
            <errorCode>string</errorCode>
            <message>string</message>
          </errorDetails>
          <shared>string</shared>
          <user>
            <email>string</email>
            <uri>string</uri>
            <userId>string</userId>
            <userName>string</userName>
          </user>
        </sharedItem>
        <sharedItem>
          <shared>string</shared>
          <user>
            <email>string</email>
            <uri>string</uri>
            <userId>string</userId>
            <userName>string</userName>
          </user>
          </sharedItem>
          </envelopes>
        </memberSharedItems>
      </sharedAccess>
      <startPosition>string</startPosition>
      <totalSetSize>string</totalSetSize>
    </accountSharedAccess>
