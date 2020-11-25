# OAuth2

## Terminology/Roles

### Resource Owner
Represents the end user with rights to access a backend resource.

### Resource Server
Remotely accessible resource (server, db...)

### Resource Client
The client app itself

### Authorization Server
Synonimous to STS or Identity Provider


## Auth0 Grant Types

### Authorization Code (+ PKCE)
Is actually all that matters to a client `Angular` App.

### Implicit
It is now effectively deprecated now that the grant type above is recommended for mobile apps, JS apps and native client apps

### Resource Owner Password Credential
Is designed for applications that have a highly trusted relationship with the STS, such as OS mechanisms to authenticate user and obtain Access Token.

### Client Credential
Service to service communication where there is no End User in the loop.

## Token types

### Access Token
Tipically a `JWT` encoding important information about the user and session, used to manage the secure communication with the backend APIs.
Encoded data includes:
* Client ID -> Representing the client app identity with the STS
* Subject Identified -> Id for the end user in the STS
* Issuer -> Information about which ID provider issued the access token
* Issue timestamp
* Issue expiration
* Audience -> Api resources that the token allows access to
* Scope claims -> Access control identifiers that allow for more fine grain controls
* Aditional Claims -> Up to the STS to implement

The information included in the `JWT` is really meant to be consumed by the Resource Server the token belongs to:
* Decode Token
* Validate signature and expiration
* Authorize calls
* Expose Security Context API to Client


## Refresh Token
Not applicable to Browser Client Applications, because they are a Long Lifetime token that can be used to issue other Access Tokens, if you expose those Refresh Tokens, it can be accessed by the Debugger Tools and be used to Issue valid Access Tokens to potentially unauthorized clients.

