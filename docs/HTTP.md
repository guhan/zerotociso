# HTTP

## What are the HTTP response codes?

- Informational Responses (1xx):
  - 100 - Continue
  - 101 - Switching Protocols
  - 102 - Processing
- Successful Responses (2xx):
  - 200 - OK
  - 201 - Created
  - 204 - No Content
  - 206 - Partial Content
- Redirection Messages (3xx):
  - 301 - Moved Permanently
  - 302 - Found
  - 304 - Not Modified
  - 307 - Temporary Redirect
  - 308 - Permanent Redirect
- Client Error Responses (4xx):
  - 400 - Bad Request
  - 401 - Unauthorized
  - 403 - Forbidden
  - 404 - Not Found
  - 409 - Conflict
  - 429 - Too Many Requests
- Server Error Responses (5xx):
  - 500 - Internal Server Error
  - 501 - Not Implemented
  - 503 - Service Unavailable
  - 504 - Gateway Timeout

## What are the HTTP headers?

The **request** headers include:
```
Request Method: GET
Request URL: /example-page
HTTP Version: HTTP/1.1
Host: The domain name of the server being accessed (www.example.com)
User-Agent: The user agent string that identifies the client making the request (in this case, a Chrome browser on Windows)
Accept: The types of content that the client can accept (text/html, application/xhtml+xml, etc.)
Accept-Language: The preferred language for the response content (en-US, en;q=0.9)
```
The **response** headers include:
```
HTTP Version: HTTP/1.1
Status Code: 200 OK
Content-Type: The type of content being returned (text/html; charset=utf-8)
Content-Length: The length of the response content in bytes
Date: The date and time the response was generated
Server: The server software that generated the response (Apache/2.4.41 in this case)
```

## What are some security HTTP headers to set?

- **Content Security Policy (CSP)**:
```
Content-Security-Policy
Content-Security-Policy-Report-Only
```
The Content Security Policy header helps prevent Cross-Site Scripting (XSS) attacks by defining a policy for allowed sources of various types of content (e.g., scripts, stylesheets, images). It helps restrict the execution of malicious scripts injected into your web pages.


- **Strict-Transport-Security (HSTS**):
Strict-Transport-Security
HSTS ensures that a website is only accessed via HTTPS, preventing attackers from downgrading the connection to plain HTTP. It helps protect against man-in-the-middle attacks and improves the overall security of communications.

- **X-Content-Type-Options**:
```
X-Content-Type-Options: nosniff
```
The X-Content-Type-Options header prevents browsers from MIME-sniffing or guessing the content type of a response. It helps protect against content type-based attacks, such as serving a malicious script with an incorrect content type.


- **X-Frame-Options**:
```
X-Frame-Options: DENY or SAMEORIGIN
```
The X-Frame-Options header prevents your web pages from being displayed in a frame or iframe on another website. This mitigates clickjacking attacks, where an attacker tries to trick users into interacting with hidden or disguised elements on a webpage.


- **X-XSS-Protection**:
```
X-XSS-Protection: 1; mode=block
```
The X-XSS-Protection header enables the built-in XSS (Cross-Site Scripting) filter of modern browsers. It helps detect and block certain types of reflected XSS attacks, providing an additional layer of protection against XSS vulnerabilities.

- **Referrer-Policy**:
```
Referrer-Policy: strict-origin-when-cross-origin
```
The Referrer-Policy header controls what information is sent in the Referer header when navigating to another page. It helps limit the exposure of sensitive information in URLs and protects against certain types of information leakage.
