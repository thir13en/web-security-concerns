# CSRF


CSRF Attack is an attack that forces a user to do an unintended request. For example, if a website is accepting an email change request via:
```
POST /email/change HTTP/1.1
Host: site.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 50
Cookie: session=abcdefghijklmnopqrstu

email=myemail.example.com 
```
Then an attacker can easily make a form in a malicious website that sends a `POST` request to https://site.com/email/change with a hidden email field and the session cookie will automatically be included.

However, **this can be mitigated easily using `sameSite` flag in your cookie and by including an `anti-CSRF` token**.
