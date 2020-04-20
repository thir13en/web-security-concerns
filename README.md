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