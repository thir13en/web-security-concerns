# Checklist

## Check this items in your set up to make sure you minimize security flaws...

### No returned arrays from api
All returned elements are objects, in order to protect fron JSON hijacking.


### Use HTTPS
HTTPS uses Transport Layer Security (TLS) to encrypt traffic. This means communication between the client and server is encrypted. For your API, this means the content sent from your API is secured from third-parties, but more importantly it means that the access credentials are secured.

### Authenticate
Authentication is how you allow or prevent access to the API.

### Authorize
Where authentication is concerned with who the user of your API is, authorization focuses on what they have access to.

### Secure endpoints AND resources (Object level authorization)
It's common to secure an endpoint or set of endpoints through authorization. A more future-proof approach is to secure the individual resources as well. This prevents misconfigured, endpoint-level authorization from reaching your data. It also means that the endpoints themselves aren't restricted by user type, but instead the resource controls who can and cannot view it.

### Rate limit
Rate-limiting is a technique for throttling the usage of an API. It can protect your resources financially, but also ensure that your servers aren't overloaded by a flood of requests at one time. If you've ever seen the 429 HTTP status code, you've experienced rate-limiting.

### Validate and sanitize input
Client-side validation is helpful for preventing mistakes and improving the user experience, but your API needs to also validate and sanitize all input before acting on it.

### Expose only what is needed
Do not unnecessary increment the attack surface of your API.

### Configure error messages
Providing end-users with details about the structure of your internal code can open up areas for attackers to focus on. Make sure to configure error messages to provide enough information to help users debug and enough for them to report problems, but not enough to expose the inner workings of your application or sensitive data.
Don't expose sensitive info.

### Control dependencies
Make sure to assess your dependencies. Are they well maintained? Are you using the latest version? Is there a history of problems? Perhaps more importantly: Do you really need a library for what you're doing?

### Allow users to track and reset authentication keys
One additional way to improve the security of your own API is to allow users to reset their credentials and monitor their own usage.

### Standardize auth across your services
We've seen the big players in API like Google, Microsoft, and Amazon standardize the authorization and authentication process for their APIs.

### Follow standard guidelines from OWASP
In addition to these best practices, consider adopting recommendations from The Open Web Application Security Project (OWASP).
