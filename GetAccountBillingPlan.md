# Get Account Billing Plan

This returns the billing plan information for the specified account, including the current billing plan, successor plans, 
billing address, and billing credit card.

## URL

    /accounts/{accountId}/billing_plan
    
    Optional query strings: include_metadata={true or false}, 
    include_successor_plans={true or false}, 
    include_credit_card_information={true or false}

## Formats

    XML, JSON

## HTTP Method

    GET

## Parameters

    There are no required parameters.
    
    If the optional query include_metadata is true, then the canUpgrade,
    canCancelRenewal, renewalStatus information is included the response
    and an array of supportedCountriesis added to the billingAddress information.
    
    By default the successor plan and credit card information is included
    in the response. This information can be excluded from the response
    by adding the appropriate optionalquery string with the setting = false.

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/accounts/{accountId}/billing_plan
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
    <Password>{password}</Password><IntegratorKey>{integrator_key}
    </IntegratorKey></DocuSignCredentials>

## Response

The response returns the billing plan information, including the currency code, for the plan.
The billingPlan and succesorPlans parameters are the same as those shown in the [Get Billing Plan Details]
(https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Get%20Billing%20Plan%20Details.htm)
reference. the billingAddress and creditCardInformation parameters are the same as those shown in the
[Update Billing Plan](https://www.docusign.com/p/RESTAPIGuide/Content/REST%20API%20References/Update%20Account%20Billing%20Plan.htm) reference.

> **Note:** When credit card number information is shown, a mask is applied to the response 
> so that only the last 4 digits of the card number are visible.

|Name|Type|Description|
|-----|-----|--------|
|billingAddressIsCreditCardAddress|Boolean|If true, the credit card address information is the same as that returned as the billing address. If false, then the billing address is considered a billing contact address, and the credit card address can be different.|

The following example shows the response json body.
This example includes the upgrade/renewal information,
supportedCountries array (include_metadata=true),
and the successor plans and credit card information is not excluded.

### Example Response Body

    {
      "billingPlan":[{
       "planId": "String content",
        "planName":"String content",
        "paymentCycle":"String content",
        "paymentMethod":"String content",
        "perSeatPrice":"String content",
        "otherDiscountPercent":"String content",
        "supportIncidentFee":"String content",
        "supportPlanFee":"String content",
        "includedSeats":"String content",
        "enableSupport":"String content",
        "currenceyCode":"String content",
        "canUpgrade": "string",
        "canCancelRenewal": "string",
        "renewalStatus": "string",
        "seatDiscounts":[{
         "beginSeatCount":"String content",
          "discountPercent":"String content",
          "endSeatCount":"String content"
        }],
      "planFeatureSets":[{
        "featureSetId":"String content",
        "isActive":"String content",
        "name":"String content",
        "fixedFee":"String content",
        "envelopeFee":"String content",
        "seatFee":"String content"
        "isEnabled":"String content",
        "currencyFeatureSetPrices":[{
          "currencyCode":"String content",
          "fixedFee":"String content",
          "envelopeFee":"String content",
          "seatFee":"String content",
          "currencySymbol":"String content"
        }],
      }],
      },
    "successorPlans":[
      {
        "planName": "string",
        "paymentCycle": "string",
        "paymentMethod": "string",
        "perSeatPrice": "string",
        "otherDiscountPercent": "string",
        "supportIncidentFee": "string",
        "supportPlanFee": "string",
        "includedSeats": "string",
        "enableSupport": "string",
        "planId": "string",
        "seatDiscounts": [
          {
            "beginSeatCount": "string",
            "endSeatCount": "string",
            "discountPercent": "string"
         }
       ],
      "planFeatureSets": [
        {
          "featureSetId": "string",
          "isActive": "string",
          "name": "string",
          "fixedFee": "string",
          "envelopeFee": "string"
          "seatFee": "string",
          "isEnabled": "string",
          "currencyFeatureSetPrices": [
            {
              "currencyCode": "string",
              "fixedFee": "string",
              "seatFee": "string",
              "envelopeFee": "string",
              "currencySymbol": "string"
            }
          ]
        }
      ],
      "currencyPlanPrices": [
        {
          "currencyCode": "string",
          "perSeatPrice": "string",
          "supportIncidentFee": "string",
          "supportPlanFee": "string",
          "currencySymbol": "string"
          "supportedCardTypes": {
            "cardTypes": [
              "string",
              "string"
            ]
          }
        }
      ]
     }
     ],
    "billingAddress": {
      "address1": "string",
      "address2": "string",
      "city": "string",
      "state": "string",
      "postalCode": "string",
      "phone": "string",
      "fax": "string",
      "country": "string",
      "firstName": "string",
      "lastName": "string",
     "email": "string",
     "supportedCountries": [
      {
        "isoCode": "string",
        "provinceValidated": "string",
        "name": "string",
        "provinces": [
          {
            "isoCode": "string",
            "name": "string"
          },
          {
            "isoCode": "string",
             "name": "string"
          }
        ]
      },
       {
        "isoCode": "string",
        "provinceValidated": "string",
        "name": "string",
        "provinces": [
          {
             "isoCode": "string",
             "name": "string"
          },
          {
            "isoCode": "string",
            "name": "string"
          }
        ]
      }
    ]
    },
    "billingAddressIsCreditCardAddress": "string",
    "creditCardInformation": {
      "cardNumber": "string",
      "expirationMonth": "string",
      "expirationYear": "string",
      "nameOnCard": "string",
      "cardType": "string",
      "address": {
        "street1": "string",
        "street2": "string",
        "city": "string",
        "state": "string",
        "zip": "string",
        "zipPlus4": "string",
        "phone": "string",
        "fax": "string",
        "country": "string"
      }
     }
    }
