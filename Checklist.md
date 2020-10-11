# Checklist

## Check this items in your set up to make sure you minimize security flaws...

### No returned arrays from api
All returned elements are objects, in order to protect fron JSON hijacking.


By nature, APIs are meant to be used. Even if all of your users are internal, security problems can still arise. To help with this, we've assembled a list of best practices to keep in mind when securing and locking-down an API or web service.
Use HTTPS

The web has moved past standard HTTP. With browser vendors flagging URLs that don't use a secure layer, it's time to do the same for your API. HTTPS uses Transport Layer Security (TLS) to encrypt traffic. This means communication between the client and server is encrypted. For your API, this means the content sent from your API is secured from third-parties, but more importantly it means that the access credentials are secured.
Authenticate

Speaking of access credentials, the clearest way to avoid unexpected use of your API is to ensure proper authentication. Authentication is how you allow or prevent access to the API. Even publicly available APIs that are free to use should consider an authentication strategy. This allows you to limit or remove users that abuse the API, and also protect your users by giving them the ability to reset their credentials if needed. You can learn more about types of API authentication in our article on the three most common authentication methods.
Authorize

Authentication's sibling is authorization. Where authentication is concerned with who the user of your API is, authorization focuses on what they have access to. For example, free plan users may only be authorized to access a subset of your full API. When you think about integrations like social login, the user authorizes your application to read their profile data from the social platform.
Secure endpoints AND resources (Object level authorization)

It's common to secure an endpoint or set of endpoints through authorization. A more future-proof approach is to secure the individual resources as well. This prevents misconfigured, endpoint-level authorization from reaching your data. It also means that the endpoints themselves aren't restricted by user type, but instead the resource controls who can and cannot view it.
Rate limit

When we think of security, we often think of inappropriate access. It can also be useful to think of security as managing resources. Rate-limiting is a technique for throttling the usage of an API. It can protect your resources financially, but also ensure that your servers aren't overloaded by a flood of requests at one time. Many rate-limiting approaches are time-based. They can be set for a billing period to handle overall usage, as well as use a "burst" approach to limit large influxes of requests. If you've ever seen the 429 HTTP status code, you've experienced rate-limiting.
Validate and sanitize input

One of the oldest attack points for web applications is input fields. The way we access data may have changed, but the need to validate any user input hasn't. Client-side validation is helpful for preventing mistakes and improving the user experience, but your API needs to also validate and sanitize all input before acting on it. Sanitization strips malicious or invalid code from requests. Validation ensures that the data meets the necessary criteria that your resources expect. This could be type and shape, or even factors like password structure.
Expose only what is needed

It can be tempting to take a shortcut and directly map data models to endpoints. Not only can this provide overly-verbose responses and increase bandwidth usage, but it can also expose data that users don't need access to. For example, consider a /user endpoint that returns the user's profile. It may need some basic information about the user, but it doesn't need the user's password or access levels.
Configure error messages

In addition to sanitizing data that goes into your API, you'll want to sanitize the information that comes out of it. Error messages play a key role in helping users understand that a problem occurred, but make sure not to leak any sensitive data. Providing end-users with details about the structure of your internal code can open up areas for attackers to focus on. Make sure to configure error messages to provide enough information to help users debug and enough for them to report problems, but not enough to expose the inner workings of your application or sensitive data.
Don't expose sensitive info

To build on protecting sensitive data, make sure not to expose details in JSON web tokens (JWTs) or cookies. The body of a JWT have the illusion of being secure, but can easily be decoded. Because of this, you should avoid including user information that could be used to access your application. The same advice goes for URLs as well. Make sure query strings aren't exposing sensitive details.
Assess your dependencies

We no longer develop in a silo. A good portion of every codebase now contains libraries, middleware, and a variety of dependencies from outside sources. While it is generally safe to assume that popular packages are "battle-tested", that doesn't mean they aren't completely safe from vulnerabilities. Make sure to assess your dependencies. Are they well maintained? Are you using the latest version? Is there a history of problems? Perhaps more importantly: Do you really need a library for what you're doing?
Allow users to track and reset authentication keys

One additional way to improve the security of your own API is to allow users to reset their credentials and monitor their own usage. A common mistake is not allowing users to reset their API keys. If a consumer of your API exposes their key accidentally, or it is taken maliciously, the problem now directly affects your API. Instead, create a means for them to manage access.
Standardize auth across your services

We've seen the big players in API like Google, Microsoft, and Amazon standardize the authorization and authentication process for their APIs. Consider a centralized means of doing this, like using an API gateway or a dedicated point of entry for handling authentication requests.
Follow standard guidelines from OWASP

In addition to these best practices, consider adopting recommendations from The Open Web Application Security Project (OWASP). They offer platform-specific guides as well as an upcoming API-specific guide, The API Security Top 10. Beyond securing your API on a code-level, you'll also want to ensure that your servers and infrastructure are configured properly to avoid unauthorized access.
Protecting your API from other APIs

If your API relies on third-party APIs, consider implementing a solution like Bearer. Integrating the Bearer Agent will allow you to track, observe, react, and receive alerts when an API isn't performing as expected. Try out Bearer today, and connect with us @BearerSH.
