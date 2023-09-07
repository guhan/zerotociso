# Web Security

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






## What is XML External Entity (XXE)?

XML External Entity - similar to SSRF where a server returns sensitive or private information because of a malformed XML request for External Entity

- XML Parsing: XML is a widely used data format for exchanging structured information. When an application processes XML input, it typically uses a parser to interpret and extract data from the XML.


- External Entity: XML allows for the declaration and referencing of external entities. An external entity is a resource, such as a file or URL, that can be included or referenced within the XML document.


- Exploitation: In the case of an XXE vulnerability, an attacker can craft a malicious XML input that includes an external entity reference pointing to a sensitive file or a remote server they control. When the vulnerable application processes the XML, it resolves the external entity, potentially leading to unintended consequences.

### Steps to mitigate: 

- Input Validation: Validate and sanitize all user-supplied XML input. Reject or filter out any unexpected or potentially malicious content.
Disable External Entities: Configure the XML parser to disable the processing of external entities or limit their usage to trusted sources only.
- Use Safe APIs: Use secure XML parsing libraries or APIs that have built-in protection against XXE vulnerabilities, such as disabling external entity resolution by default.
- Content-Type Checking: Validate the Content-Type of incoming XML requests to ensure they match the expected XML format.
- Least Privilege: Run the server processes with the least privileges required to mitigate the potential impact of XXE attacks.

## What is HSTS?

HTTP Strict Transport Security. It is a security mechanism implemented in web browsers and web servers to enforce the use of secure connections over HTTPS (HTTP over SSL/TLS) 

Basically force HTTPS

- Initial Connection: When a client (web browser) makes the initial connection to a website that supports HSTS, the server responds with a special HTTP header called the Strict-Transport-Security header.
- HSTS Header: The Strict-Transport-Security header includes a policy directive with a specified duration. For example:
Strict-Transport-Security: max-age=31536000

- HSTS Preloading: Websites can also opt to be included in the HSTS preload list maintained by web browsers. This list is hardcoded into the browser, and websites included in the list are always accessed via HTTPS, even for the first visit






## What is Cross Site Scripting (XSS)?
allows attackers to inject malicious scripts (referred to as "payloads") into web pages viewed by other users. XSS attacks occur when an application fails to properly sanitize or validate user-supplied input

### XSS vulnerabilities can be categorized into different types based on the context in which the payload is executed:
- Stored XSS (Persistent XSS): The injected payload is permanently stored on the target server and is later retrieved and displayed to other users. For example, a malicious script injected into a forum post or a user profile that is displayed to visitors.
- Reflected XSS (Non-Persistent XSS): The injected payload is embedded within a URL or a form input, and it is reflected back in the server's response. The attack relies on tricking users into clicking on a specially crafted link that contains the payload, leading to its execution.

Reflected XSS vulnerabilities often occur when user input is directly incorporated into HTML templates, URLs, or other dynamic content without proper encoding or validation.

- DOM-based XSS: This type of XSS occurs when the payload is processed and executed by the browser's Document Object Model (DOM), rather than by the server. The attack involves manipulating the DOM structure or properties in a way that triggers the execution of the malicious code.

### To mitigate: 
- Input Sanitization: Ensure that all user-supplied input is properly validated, encoded, or sanitized before being displayed on a web page to prevent the execution of malicious code.
- Output Encoding: Use proper output encoding techniques to ensure that user-supplied data is displayed as plain text or as escaped HTML, preventing any interpretation of injected code.
- Content Security Policy (CSP): Implement a Content Security Policy that restricts the types of content that can be loaded and executed on a web page, effectively reducing the impact of XSS attacks.
- Security Testing: Regularly perform security testing, including vulnerability scanning and penetration testing, to identify and address any XSS vulnerabilities in your web applications.

## What is a Content Security Policy (CSP)?
CSP allows web developers to specify a set of rules and restrictions regarding the types of content that can be loaded and executed on a web page

- Policy Definition: A Content Security Policy is defined by a set of directives that instruct the browser on what content is allowed to be loaded or executed on a web page. The directives can be specified in the HTTP response headers or within a meta tag in the HTML of the web page.
Here's an example of a Content Security Policy (CSP) declaration that demonstrates some common directives:
```
Content-Security-Policy: default-src 'self'; script-src 'self' https://trusted-domain.com; style-src 'self' https://trusted-domain.com; img-src 'self' data:; font-src'self'; object-src 'none'; frame-src 'self'; upgrade-insecure-requests;
```
  - default-src: Sets the default policy for all content types that do not have specific directives. In this case, the default source is set to 'self', allowing resources to be loaded from the same origin.


  - script-src: Specifies the allowed sources for JavaScript code. In this example, scripts are allowed to be loaded from the same origin ('self') and from the domain https://trusted-domain.com. Scripts from any other domain will be blocked.


  - style-src: Defines the allowed sources for stylesheets. Similarly, stylesheets are allowed from the same origin ('self') and from the domain https://trusted-domain.com.


  - img-src: Determines the allowed sources for images. In this case, images can be loaded from the same origin ('self') and from the data: scheme, which allows inline image data. Images from external domains are blocked.


  - font-src: Specifies the allowed sources for web fonts. Here, fonts are allowed to be loaded from the same origin ('self'), but not from any external domains.


  - object-src: Sets the allowed sources for plugins, such as Flash or Java applets. In this example, no external sources are allowed ('none').


  - frame-src: Determines the allowed sources for frames or iframes. Frames from the same origin are allowed ('self'), while frames from other domains will be blocked.


  - upgrade-insecure-requests: This directive is not specific to any content type but instructs the browser to upgrade insecure requests (HTTP) to secure requests (HTTPS) automatically.


