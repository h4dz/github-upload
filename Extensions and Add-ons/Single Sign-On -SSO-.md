---
title: "Single Sign-On (SSO)"
excerpt: ""
---
Customers on our [Platform Business and Enterprise pricing plans](https://www.pagerduty.com/pricing/) have access to Single Sign-On. If your account is on one of these plans, the **Account Owner** can access SSO settings by going to **Configuration** :fa-arrow-right: **Account Settings** :fa-arrow-right: **Single Sign-On**.

With single sign-on, you get:

1. One-click corporate login: This eliminates the need for a separate PagerDuty username and password, which means one less thing to remember.

2. On-demand user provisioning: PagerDuty user accounts are created on-demand once access is granted via the SSO provider.

3. Revoke user access: When an employee leaves the company, administrators can remove PagerDuty access within the SSO provider rather than having to log directly into PagerDuty.
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "Revoking a user's access at your SSO provider will prevent the user from logging in via SSO, but will not delete the user in PagerDuty. You must still log in to PagerDuty to delete the user."
}
[/block]

[block:api-header]
{
  "title": "Redirect Non-Provisioned Users"
}
[/block]
Auto-provisioning users can get responders up and running quickly, but it will affect billing. If you do not wish to auto-provision users, the Account Owner can optionally redirect non-provisioned users to a destination link, such as an internal wiki, for more information about getting provisioned in your identity provider.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/34f6e06-Screen_Shot_2018-02-07_at_3.15.38_PM.png",
        "Screen Shot 2018-02-07 at 3.15.38 PM.png",
        1106,
        290,
        "#ebebea"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Common Identity Providers"
}
[/block]
You can find step-by-step guides for configuring many common identity providers (IdP) in the [PagerDuty Extensions Directory](https://www.pagerduty.com/integrations#extensions).

### Shibboleth Configuration Help

You can hand-craft a metadata file if you wish. The contents should look similar to the following. Be sure to replace `subdomain` with your own PagerDuty subdomain.

In addition to configuration via metadata, a RelyingParty configuration, such as shown the example below, will need to be created in Shibboleth. Be sure to replace the provider URL with your own.

```
<rp:RelyingParty 
id="https://subdomain.pagerduty.com" 
provider="https://domain/idp/shibboleth" 
defaultAuthenticationMethod="urn:oasis:names:tc:SAML:2.0:ac:classes:unspecified" 
defaultSigningCredentialRef="IdPCredential"> 
<rp:ProfileConfiguration xsi:type="saml:SAML2SSOProfile" 
includeAttributeStatement="true" 
assertionLifetime="300000" 
assertionProxyCount="0" 
signResponses="conditional" 
signAssertions="never" 
signRequests="conditional" 
encryptAssertions="never" 
encryptNameIds="never" 
/> 
</rp:RelyingParty>
```
[block:api-header]
{
  "title": "Custom SAML Configuration"
}
[/block]
For custom SAML configurations, we provide the following metadata URL to make your configuration easier:

```
https://{subdomain}.pagerduty.com/sso/saml/metadata
```

## Required Attributes

For manual SAML configurations, we will validate and enforce the following attributes in the SAML payload:

1. Destination (sometimes labeled SAML Recipient in IdP configuration forms) is expected to be: 

```
https://{subdomain}.pagerduty.com/sso/saml/consume
```

2. Audiences (sometimes labeled SAML Audience in IdP configuration forms) is expected to be:

```
https://{subdomain}.pagerduty.com
```
[block:callout]
{
  "type": "warning",
  "title": "Important",
  "body": "There should be no trailing slash. Users will receive an `HTTP 400` error when trying to log in if there is a `/` after your subdomain."
}
[/block]
3. Name ID is expected to be the user's email address:

```
urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress
```

## Optional Attributes for Auto-Provisioning

* User names will be set to the value of the `Name` or `name` attribute we receive in your SAML payload. If there is no `Name` or `name` attribute in your SAML payload then the user's name will default to their email address.

* User roles will be set to the value of the `Role` or `role` attribute we receive, where the value must match one of our [REST API user role values](https://v2.developer.pagerduty.com/v2/page/api-reference#!/Users/post_users): `admin`, `limited_user`, `user` or `read_only_user` (known as Stakeholder user). Accounts with [Advanced Permissions](https://support.pagerduty.com/v1/docs/advanced-permissions) may also pass an `observer` role. If there is no `Role` or `role` attribute in your SAML payload then the user's role will default to the [User role](doc:user-roles).

* The job title of the user will be derived from the  `jobresponsibilities` attribute in the SAML payload, if present.
[block:callout]
{
  "type": "info",
  "body": "These attributes will only be used when a user is initially created. Changing the user's email address, name, or role in your IdP will not change these values in PagerDuty; you will still need to update a user's login email address, name, or role in PagerDuty if you change them in your IdP after the user has already been automatically provisioned in PagerDuty.",
  "title": "Note"
}
[/block]

[block:api-header]
{
  "title": "User Log In via SSO"
}
[/block]
To log in using SSO:

1. Ensure that you are logged in to your identity provider (e.g. Okta, OneLogin, etc).
2. Go to your PagerDuty account at `https://[your-pagerduty-subdomain].pagerduty.com/sign_in`.
3. Click the green **Sign In With Your Identity Provider** button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/edb143c-sso-sign-in.png",
        "sso-sign-in.png",
        710,
        1038,
        "#e2eddb"
      ]
    }
  ]
}
[/block]
4. Your identity provider will automatically sign you into your PagerDuty account. 
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "If you do not see the **Sign In With Your Identity Provider** button, or if you are unable to log in to your account, please contact your Account Owner to [troubleshoot](https://support.pagerduty.com/docs/sso#section-troubleshooting-tips) and ensure that SSO has been properly configured."
}
[/block]

[block:api-header]
{
  "title": "Troubleshooting Tips"
}
[/block]
## Error "Account saml configuration x509 cert is invalid" in the web app after inserting your x509 cert

1. Confirm that you are using a valid x509 certificate. 
2. Confirm that each row in your x.509 certificate is a maximum of 64 characters.
3. Confirm there is the text `-----BEGIN CERTIFICATE-----` at the beginning of the certificate and `-----END CERTIFICATE-----` at the end of the certificate.
[block:api-header]
{
  "title": "FAQ"
}
[/block]
## Can I use a self-signed certificate for my SAML SSO integration?

Yes. PagerDuty will treat signatures from the identity provider as valid as long as:

* The certificate stored in the PagerDuty SAML settings matches the private key that the identity provider uses to sign SAML responses, and:
* The identity provider is configured to sign assertions.

Once these conditions have been met, users should be able to authenticate.
[block:callout]
{
  "type": "warning",
  "body": "If configuring an on-premises identity provider, you should treat its private key with utmost secrecy and take adequate security precautions."
}
[/block]