# Cross Site Request Forgery (CSRF)

## What is Cross Site Request Forgery? 

an attacker tricks a victim into performing unwanted actions on a website where the victim is authenticated. 
```
User logs into Site A and is authenticated, get a cookie 
Attacker lures User to Site B 
Site B makes requests to Site A on users behalf because users browser is already authenticated on Site A
```
## How do you prevent CSRF? 
- **CSRF Tokens**: Use CSRF tokens for all sensitive operations. These tokens are unique per user session and embedded in forms or requests. The server validates the token with each request to ensure it originated from the same site and is not forged.

- **Same-Site Cookies**: Configure cookies with the "SameSite" attribute set to "Strict" or "Lax". This prevents cookies from being sent with cross-site requests, mitigating CSRF attacks.
When a web server sets a SameSite attribute on a cookie, it instructs the user's browser to include that cookie only in requests that originate from the same site as the one that set the cookie

- **Referer Header Validation**: Validate the "Referer" header on the server side to ensure that requests originate from the same site. However, note that the Referer header can be spoofed or omitted in some cases.

- **Anti-CSRF Libraries**: Utilize security libraries or frameworks that provide built-in protection against CSRF attacks. These libraries handle the generation and validation of CSRF tokens automatically.

- **Logout CSRF Protection**: Implement protection mechanisms to prevent CSRF attacks even after a user has logged out. For example, invalidate session cookies upon logout and enforce re-authentication for sensitive actions.

## What is a nonce?

Nonces are unique tokens generated by the server


## How does a CSRF token work?

- **Unpredictable Token**: CSRF tokens are random and unique for each user session. When a user authenticates on a website, a CSRF token is generated and associated with their session. This token is unpredictable and not known to the attacker.
- **Token Verification**: When a user performs an action that requires CSRF protection (e.g., submitting a form), the server includes the CSRF token in the request, either as a hidden field in an HTML form or as a header or parameter in AJAX requests.
- **Token Validation**: Upon receiving the request, the server validates the CSRF token's authenticity. It checks if the token sent by the client matches the one associated with the user's session. If the tokens match, the request is considered valid and processed. If the tokens do not match or are missing, the server can reject the request as a potential CSRF attack.

## What are SameSite cookies?

​​- **Strict**: When the SameSite attribute is set to "Strict", the cookie will only be sent in requests that originate from the same site. It will not be sent in cross-site requests, including those initiated by links from external websites or resources.
- **Lax**: With the "Lax" value, the cookie is sent in cross-site requests that are considered "safe." Safe requests typically include top-level navigation by clicking on links, but not requests made by including resources from external websites (e.g., loading images or scripts).
- **None**: When the SameSite attribute is set to "None", the cookie is sent in all cross-site requests. However, to use this value, the cookie must also be marked as secure (using the "Secure" attribute) to ensure that it is only sent over secure HTTPS connections.

## Can any server access all cookies in a browser?
In general, No, a server cannot directly access cookies set by other websites or domains. Cookies are specific to the domain that set them, and they are intended to be accessible only by that domain.

However **if SameSite is set to None, then the cookie is accessible by any site.** 