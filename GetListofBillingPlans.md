# Get List of Billing Plans

This returns the billing plans associated with a distributor.

## URL

    /billing_plans

## HTTP Method

    GET

## Parameters

No additional parameters are required.

## Request

### Example Request Body

    GET https://{server}/restapi/{apiVersion}/billing_plans

## Response

The response returns the billing plan information.

The following example shows the response json body.

### Example Response Body

    {
      "billingPlans":[{
        "currencyPlanPrices":[{    "enableSupport":"String content",
          "currencyCode":"String content",
          "currencySymbol":"String content",
          "perSeatPrice":"String content",
          "supportIncidentFee":"String content",
          "supportPlanFee":"String content"
        }],
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
