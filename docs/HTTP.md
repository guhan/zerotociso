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
