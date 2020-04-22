# Things to consider when building secure Web Apps

## Authentication
## Authorization

## Transport protection
#### How to enforce?
Use TLS using https protocol.

## Cross Origin Resource Sharing (CORS)
#### How to enforce?
Set up the Access-Control-Allow-Origin properly in the headers and in your server service configuration.

## Cross Site Request Forgery (CSRF)
#### How to enforce?
Sending the access token explicitly in the request header every time.

## Cross Site Scripting (XSS)
#### How to enforce?
Use a sanitizer for every Input field in your site.


# External Identity Providers
Google, Facebook, Twitter, LinkedIn

# Cloud or On Premise Identity Providers

#### Azure Active Directory
* AAD Business to Consumer (B2C): OpenID support and works on all accounts, not only MS

#### Identity as a Service Providers
* Auth0
* Ping
* Okta

#### Identity Server 4
* Open Source Identity Provider Framework
* Requires set up and configuration
* Requires to be hosted in a VM
* Most flexible option for Single Sign On (SSO) federation scenarios


# JavaScript Clients

#### Angular JWT
Only manages jwt tokens and is up to you to manage connection with Identity Provider

#### ADAL
Specific for Azure, not compliant with OpenID

#### MSAL
Specific for Azure, compliant with OpenID Connect Standard

#### oidc-client
Fully protocol compliant implementation of the client OpenID flows that is not attached to any specific Identity Provider (recommended)