# Get Billing Charges

This returns the list of recurring and usage charges for the account.
This can be used to determine the charge structure and usage of charge plan items.
This call can only be used by users with account administrator privileges.

## URL

    /accounts/{accountId}/billing_charges

## HTTP Method

    GET

## Parameters

There are no required parameters.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/billing_charges
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                               <Password>{password}</Password><IntegratorKey>
                               {integrator_key}</IntegratorKey></DocuSignCredentials>
                               
    Accept: application/json
    Content-Type: application/json

## Response

The response returns a list of charges and information about the charges.
Quantities are usually shown as ‘unlimited’ or an integer.
Amounts are shown in the currency set for the account.

The following table provides a description of the different chargeName values.
The information will grow as more chargeable items are added to the system.

|chargeName|Description|
|----------|-----------|
|id_check|ID Check Charge|
|in_person_signing|In Person Signing charge|
|envelopes	Included|Sent Envelopes for the account|
|age_verify|Age verification check|
|ofac|OFAC Check|
|id_confirm|ID confirmation check|
|student_authentication|STAN PIN authentication check|
|wet_sign_fax|Pages for returning signed documents by fax&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|attachment_fax|Pages for returning attachments by fax|
|phone_authentication|Phone authentication charge|
|powerforms|PowerForm envelopes sent|
|signer_payments|Payment processing charge|
|outbound_fax|Send by fax charge|
|bulk_recipient_envelopes|Bulk Recipient Envelopes sent|
|sms_authentications|SMS authentication charge|
|saml_authentications|SAML authentication charge|
|express_signer_certificate|DocuSign Express Certificate charge|
|personal_signer_certificate&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Personal Signer Certificate charge|
|safe_certificate|SAFE BioPharma Signer Certificate charge|
|seats|Included active seats charge|
|open_trust_certificate|OpenTrust Signer Certificate charge|

The following example shows the response json body.

### Example Response Body

    {
      "billingChargeItems": [
        {
         "chargeName": "string",
         "chargeType": "string",
         "chargeUnitOfMeasure": "string",
         "allowedQuantity": "string",
         "usedQuantity": "string",
         "includedQuantity": "string",
         "firstEffectiveDate": "string",
         "lastEffectiveDate": "string",
         "unitPrice": "string",
         "blocked": "string",
         "prices": [
           {
             "unitPrice": "string",
             "beginQuantity": "string",
             "endQuantity": "string"
           },
           {
             "unitPrice": "string",
             "beginQuantity": "string",
             "endQuantity": "string"
           }
         ],
          "discounts": [
           {
            "endQuantity": "string",
            "beginQuantity": "string",
            "discount": "string"
           },
           {
            "endQuantity": "string",
            "beginQuantity": "string",
            "discount": "string"
           }
         ]
        },
      {
        "chargeName": "string",
        "chargeType": "string",
        "chargeUnitOfMeasure": "string",
        "allowedQuantity": "string",
        "usedQuantity": "string",
        "includedQuantity": "string",
        "firstEffectiveDate": "string",
        "lastEffectiveDate": "string",
        "unitPrice": "string",
        "blocked": "string",
        "prices": [
          {
            "unitPrice": "string",
            "beginQuantity": "string",
            "endQuantity": "string"
          },
          {
            "unitPrice": "string",
            "beginQuantity": "string",
            "endQuantity": "string"
          }
       ],
          "discounts": [
           {
            "endQuantity": "string",
            "beginQuantity": "string",
            "discount": "string"
           },
           {
            "endQuantity": "string",
            "beginQuantity": "string",
            "discount": "string"
           }
         ]
      }
      ]
    }
