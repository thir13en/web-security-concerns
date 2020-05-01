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