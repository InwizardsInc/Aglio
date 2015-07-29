# Upload Brand Profiles

This is used to upload one or more brand profile files for the account.
The Account Branding feature (accountSettings “canSelfBrandSend” and “canSelfBrandSign” are true)
must be enabled for the account to use this.

When uploading brand profile files, if the brandId for a brand profile already
exisits for the account, an error is returned. If you want to upload a new version
of an existing brand profile, you should delete the profile and then upload the newer version.

When brand profile files are being uploaded, they must be combined into
one zip file and the Content-Type must be application/zip.

## URL

    /accounts/{accountId}/brands

## HTTP Method

    POST

## Parameters

No additional parameters are required.

## Request

    POST https://{server}/restapi/{apiVersion}/accounts/{accountId}/brands
    X-DocuSign-Authentication: <DocuSignCredentials><Username>{name}</Username>
                              <Password>{password}</Password><IntegratorKey>{integrator_key}
                              </IntegratorKey></DocuSignCredentials>
    Accept: application/json
    Content-Type: application/zip
   
    <base64bytes brand zip file removed for brevity>

## Response

The response returns if the upload is successful and the default brand profile for the account and a list of brand profiles added to the account.

The following example shows the response json body.

### Example Request Body

    {
      "brands":[
        {
          "brandCompany":"String content"
          "brandId":"String content",
          "brandName":"String content"
        },
        {
          "brandCompany":"String content"
          "brandId":"String content",
          "brandName":"String content"
        }
      ]
      "recipientBrandIdDefault":"String content",
      "senderBrandIdDefault":"String content",
    }
