# Get Billing Plan Details

This returns the billing plan details for the specified billing plan ID.

## URL

    /billing_plans/{planId}

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/billing_plans/{planId}
    
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username><Password>
                              {password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>

## Response

The response returns the Billing plan and Successor plan details. The plan details are described below.

|Name|Type|Description|
|----|----|-----------|
|currencyPlanPrices||A complex type that contains the alternate currency values for perSeatPrice, supportIncidentFee, supportPlanFee that are configured for this plan. It also includes the alternate currencyCode, currenceySymbol, and a list of accepted credit card types.|
|enableSupport|Boolean|If true the plan has support enabled.|
|includedSeats|Integer|The number of seats included in the plan.|
|otherDiscountPercent|Decimal|Any other percentage discount for the plan.|
|paymentCycle|String|The payment cycle associated with the plan. The possible values are: Monthly or Annually.|
|paymentMethod|String|The payment method used with the plan. The possible values are: CreditCard, PurchaseOrder, Premium, or Freemium.|
|perSeatPrice|Decimal|The per seat price for the plan.|
|planFeatureSets||A complex type that sets the feature sets for the account. It contains the following information (all string content):<ul><li>currencyFeatureSetPrices - This contains the currencyCode and currencySymbol for the alternate currency values for envelopeFee, fixedFee, seatFee that are configured for this plan feature set.</li><li>envelopeFee - An incremental envelope cost for plans with envelope overages (when isEnabled=true).</li><li>featureSetId - A unique ID for the feature set.</li><li>fixedFee - A one-time fee associated with the plan (when isEnabled=true).</li><li>isActive - Determines if the feature set is actively set as part of the plan.</li><li>isEnabled - Determines if the feature set is actively enabled as part of the plan.</li><li>name - The name of the feature set.</li><li>seatFee - An incremental seat cost for seat-based plans (when isEnabled=true).</li></ul>|
|planId|String|The plan ID for the account. It uniquely identifies a plan and is used to set plans in other functions.|
|planName|String|The name of the plan.|
|seatDiscounts|seatDiscount|A complex type that return any seat discount information.<br/>It contains the information: BeginSeatCount, EndSeatCount and SeatDiscountPercent.|
|supportIncidentFee|Decimal|The support incident fee charged for each support incident.|
|supportPlanFee|Decimal|The support plan fee charged for this plan.|

<br/>
The following example shows the response json body.
<br/>

### Example Response Body

    {
      "billingPlan":{
        "currencyPlanPrices":[{
      "currencyCode":"String content",
      "currencySymbol":"String content",
      "perSeatPrice":"String content",
      "supportIncidentFee":"String content",
      "supportPlanFee":"String content"
      "supportedCardTypes": {
        "cardTypes": [
          "string",
          "string"
        ]
      }
        }],
        "enableSupport":"String content",
        "includedSeats":"String content",
        "otherDiscountPercent":"String content",
        "paymentCycle":"String content",
        "paymentMethod":"String content",
        "perSeatPrice":"String content",
        "planFeatureSets":[{
          "currencyFeatureSetPrices":[{
            "currencyCode":"String content",
            "currencySymbol":"String content",
            "envelopeFee":"String content",
            "fixedFee":"String content",
            "seatFee":"String content"
          }],
          "envelopeFee":"String content",
          "featureSetId":"String content",
          "fixedFee":"String content",
          "isActive":"String content",
          "isEnabled":"String content",
          "name":"String content",
          "seatFee":"String content"
        }],
        "planId":"String content",
        "planName":"String content",
        "seatDiscounts":[{
          "beginSeatCount":"String content",
          "discountPercent":"String content",
          "endSeatCount":"String content"
        }],
        "supportIncidentFee":"String content",
        "supportPlanFee":"String content"
      },
      "successorPlans":[{
        "currencyPlanPrices":[{
          "currencyCode":"String content",
          "currencySymbol":"String content",
          "perSeatPrice":"String content",
          "supportIncidentFee":"String content",
          "supportPlanFee":"String content"
        }],
        "enableSupport":"String content",
        "includedSeats":"String content",
        "otherDiscountPercent":"String content",
        "paymentCycle":"String content",
        "paymentMethod":"String content",
        "perSeatPrice":"String content",
        "planFeatureSets":[{
          "currencyFeatureSetPrices":[{
            "currencyCode":"String content",
            "currencySymbol":"String content",
            "envelopeFee":"String content",
            "fixedFee":"String content",
            "seatFee":"String content"
          }],
          "envelopeFee":"String content",
          "featureSetId":"String content",
          "fixedFee":"String content",
          "isActive":"String content",
          "isEnabled":"String content",
          "name":"String content",
          "seatFee":"String content"
        }],
        "planId":"String content",
        "planName":"String content",
        "seatDiscounts":[{
          "beginSeatCount":"String content",
          "discountPercent":"String content",
          "endSeatCount":"String content"
        }],
        "supportIncidentFee":"String content",
        "supportPlanFee":"String content"
      }]
    }
