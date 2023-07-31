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



## What Is SSL encryption?
SSL (Secure Sockets Layer) encryption, also commonly referred to as TLS (Transport Layer Security) encryption, is a cryptographic protocol used to secure communication over a network

- **Handshake**: The SSL/TLS handshake is the initial process where the client and server establish a secure connection. During the handshake, they negotiate encryption algorithms, exchange cryptographic keys, and verify the authenticity of each other's identity (through digital certificates).


- **Encryption**: Once the secure connection is established, SSL/TLS encryption is applied to protect the data transmitted between the client and server. Encryption algorithms, such as symmetric encryption (e.g., AES) and asymmetric encryption (e.g., RSA), are used to encrypt and decrypt data. This ensures that even if intercepted, the data is unreadable without the appropriate decryption keys.


- **Data Integrity**: SSL/TLS also provides data integrity, which means that the data sent between the client and server cannot be altered or tampered with during transit. This is achieved through the use of cryptographic hash functions, such as SHA (Secure Hash Algorithm), which generate unique checksums for the data. These checksums are used to verify the integrity of the received data.


- **Authentication**: SSL/TLS supports server authentication, where the server presents a digital certificate to prove its identity to the client. The certificate is issued by a trusted Certificate Authority (CA) and contains the server's public key. The client verifies the certificate to ensure it is valid and issued by a trusted source, establishing trust in the server's identity.


- **Mutual Authentication** (Optional): SSL/TLS can also support mutual authentication, where both the client and server authenticate each other. In this scenario, the client presents its own digital certificate to the server, allowing the server to verify the client's identity.

## What is the difference between ssl and tls?

- TLS is the recommended protocol for securing internet communication. TLS provides stronger encryption algorithms, improved key exchange mechanisms, and enhanced security features compared to SSL. 

- TLS 1.0 was introduced as the successor to SSL 3.0, followed by TLS 1.1, TLS 1.2, and TLS 1.3, each providing improved security features and performance enhancements.



## How does a client check a servers SSL certificate?

- **Certificate Validation**: The client receives the SSL certificate from the server during the SSL/TLS handshake process. The certificate contains the server's public key, server information, and is digitally signed by a trusted Certificate Authority (CA).


- **Certificate Chain**: The client checks the certificate chain to establish trust. This involves verifying the authenticity and validity of each certificate in the chain. The chain typically includes the server's SSL certificate, intermediate certificates (if any), and the root certificate.


- **Root Certificate Verification**: The client has a list of trusted root certificates stored in its certificate store or trusted certificate authorities. It verifies if the root certificate that signed the server's SSL certificate is present in this list. If the root certificate is not trusted or missing, the client may display a warning or reject the connection.


- **Certificate Expiry and Revocation**: The client checks the expiration date mentioned in the SSL certificate to ensure it is not expired. It also checks for certificate revocation by verifying if the certificate has been revoked by the issuing CA. This is done by checking Certificate Revocation Lists (CRLs) or using Online Certificate Status Protocol (OCSP) services.


- **Hostname Verification**: The client verifies that the common name (CN) or subject alternative names (SANs) in the certificate match the hostname to which the client is connecting. This ensures that the server's certificate is issued for the correct domain or server.


- **Certificate Integrity**: The client verifies the integrity of the certificate by checking the digital signature. It uses the public key of the issuing CA to validate the signature and ensure that the certificate has not been tampered with or modified.


## How does the SSL/TLS handshake work?

1. Client Hello: The client initiates the handshake by sending a Client Hello message to the server. This message contains information such as the SSL/TLS version supported by the client, a random value (Client Random), and a list of supported cipher suites and compression methods.
2. Server Hello: Upon receiving the Client Hello, the server responds with a Server Hello message. This message includes the SSL/TLS version selected by the server, a random value (Server Random), the chosen cipher suite, and the server's digital certificate (if required).
3. Certificate Exchange: If the server's certificate is required for authentication, it sends its digital certificate to the client. The certificate contains the server's public key, identity information, and is signed by a trusted Certificate Authority (CA).
4. Client Key Exchange: The client generates a pre-master secret and encrypts it with the server's public key from the received certificate. The encrypted pre-master secret is sent to the server, ensuring that only the server can decrypt it with its private key.
5. Server Key Exchange (optional): In some cases, the server may send additional information or parameters required for the key exchange, such as Diffie-Hellman parameters or a server key exchange message.
6. Certificate Verification: The client verifies the authenticity and validity of the server's certificate. It checks the digital signature, expiration date, and checks if the certificate has been revoked or issued by a trusted CA. If the verification fails, the client may display a warning or terminate the connection.
7. Pre-Master Secret Derivation: Both the client and server independently compute the pre-master secret using the exchanged keys. This pre-master secret is used to generate the session keys required for encryption and decryption.
8. Session Key Generation: Using the pre-master secret, the client and server independently generate the session keys used for symmetric encryption and decryption during the secure communication.
9. Handshake Completion: Finally, both the client and server send a Finished message, which includes a hash of all the exchanged messages during the handshake. This allows both parties to verify the integrity of the handshake and ensure that the communication parameters match.


## What is the same-origin policy and CORS?

An origin is a combination of the protocol, domain, and port number of a web page's URL

The Same origin policy (SOP) aims to prevent malicious scripts from accessing or manipulating data from different origins, thereby protecting user privacy and security.
According to the Same Origin Policy:
- Origin Restriction: Web content, such as JavaScript, HTML, and XMLHTTPRequests, can only interact with resources (e.g., scripts, cookies, or data) from the same origin. The origin includes the same protocol (e.g., HTTP or HTTPS), domain (e.g., example.com), and port number (e.g., 80 for HTTP, 443 for HTTPS).

**important to note that the SOP is enforced by web browsers and can be bypassed through various vulnerabilities or misconfigurations**

- Use Relative URLs
Set header Access-Control-Allow-Origin: <origin>

- Cross-Origin Resource Sharing (CORS): CORS is a mechanism that allows servers to specify which origins are permitted to access their resources. It includes HTTP headers that the server sends in its response to inform the browser about cross-origin permissions.

  - Access-Control-Allow-Origin: https://example.com, https://anotherdomain.com
  - Access-Control-Allow-Methods: Specifies the HTTP methods (e.g., GET, POST, PUT, DELETE) that are allowed for cross-origin requests.
  - Access-Control-Allow-Headers: Specifies the additional HTTP headers (e.g., Authorization, Content-Type) that are allowed for cross-origin requests.
  - Access-Control-Allow-Credentials: Indicates whether the server allows credentials (such as cookies or HTTP authentication) to be included in cross-origin requests. This header is set to true or false.
  - Access-Control-Max-Age: Specifies the maximum duration (in seconds) for which the preflight response (OPTIONS request) can be cached.



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



## What is Server Side Request Forgery (SSRF)?

An attacker can make a server perform unintended requests to other internal or external resources

Examples: 
```
POST /product/stock HTTP/1.0
Content-Type: application/x-www-form-urlencoded
Content-Length: 118

stockApi=http://192.168.0.68/admin
```
(where 192.168.0.68 is a different server on the local network of the server the POST request is being sent to)

- Accessing Internal APIs: An attacker could provide a URL that targets an internal API endpoint, such as http://internal-server/api/employee/1, which retrieves sensitive employee data. By exploiting the SSRF vulnerability, the attacker can access and retrieve the employee data that is meant to be restricted to internal use only.

- Port Scanning: The attacker could supply a URL with an IP address and a specific port, such as http://internal-server:22. If the vulnerable server is configured to perform outgoing network connections, the attacker can use SSRF to scan internal systems and identify open ports, potentially leading to further exploitation.
- Local Network Access: If the vulnerable server is deployed in a local network, an attacker could provide a URL that targets local resources, such as http://192.168.0.1, which represents the local router's administration interface. Exploiting the SSRF vulnerability, the attacker can access and manipulate the router's settings, potentially gaining control over the network.
- Cloud Metadata Service: In cloud environments, instances often have access to a metadata service that provides information about the instance, such as instance details, credentials, or access keys. An attacker could craft a URL targeting the metadata service, such as http://169.254.169.254/latest/meta-data/credentials, and exploit the SSRF vulnerability to retrieve sensitive information from the instance metadata.
- Exploiting Internal Services: An attacker could leverage SSRF to target internal services running on the same network as the vulnerable server. For example, they could provide a URL like http://internal-service:8080/admin-panel and exploit the SSRF vulnerability to gain unauthorized access to the administrative panel of the internal service.



### Preventing SSRF
- Input Validation: Implement proper input validation and sanitization techniques to prevent attackers from manipulating URLs or injecting malicious input.


- Whitelisting: Use whitelisting techniques to allow only specific URLs or domains that are trusted and necessary for the application's functionality.


- Restrict Network Access: Configure firewalls or security groups to restrict network access and prevent the server from reaching unauthorized internal resources.


- URL Parsing and Validation: Implement strict URL parsing and validation routines to ensure that only valid and intended URLs are processed by the server.


- Least Privilege Principle: Ensure that the server making requests has the least privilege necessary and only has access to the resources it actually requires.



## What is XXE?

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


## What is Cross Site Request Forgery? 

an attacker tricks a victim into performing unwanted actions on a website where the victim is authenticated. 
```
User logs into Site A and is authenticated, get a cookie 
Attacker lures User to Site B 
Site B makes requests to Site A on users behalf because users browser is already authenticated on Site A
```
### Prevent by: 
- CSRF Tokens: Use CSRF tokens for all sensitive operations. These tokens are unique per user session and embedded in forms or requests. The server validates the token with each request to ensure it originated from the same site and is not forged.

- Same-Site Cookies: Configure cookies with the "SameSite" attribute set to "Strict" or "Lax". This prevents cookies from being sent with cross-site requests, mitigating CSRF attacks.
When a web server sets a SameSite attribute on a cookie, it instructs the user's browser to include that cookie only in requests that originate from the same site as the one that set the cookie

- Referer Header Validation: Validate the "Referer" header on the server side to ensure that requests originate from the same site. However, note that the Referer header can be spoofed or omitted in some cases.

- Anti-CSRF Libraries: Utilize security libraries or frameworks that provide built-in protection against CSRF attacks. These libraries handle the generation and validation of CSRF tokens automatically.

-  Logout CSRF Protection: Implement protection mechanisms to prevent CSRF attacks even after a user has logged out. For example, invalidate session cookies upon logout and enforce re-authentication for sensitive actions.

## What is a nonce?

Nonces are unique tokens generated by the server


## How does a CSRF token work?

- Unpredictable Token: CSRF tokens are random and unique for each user session. When a user authenticates on a website, a CSRF token is generated and associated with their session. This token is unpredictable and not known to the attacker.


- Token Verification: When a user performs an action that requires CSRF protection (e.g., submitting a form), the server includes the CSRF token in the request, either as a hidden field in an HTML form or as a header or parameter in AJAX requests.
- Token Validation: Upon receiving the request, the server validates the CSRF token's authenticity. It checks if the token sent by the client matches the one associated with the user's session. If the tokens match, the request is considered valid and processed. If the tokens do not match or are missing, the server can reject the request as a potential CSRF attack.


## What are SameSite cookies?

​​- Strict: When the SameSite attribute is set to "Strict", the cookie will only be sent in requests that originate from the same site. It will not be sent in cross-site requests, including those initiated by links from external websites or resources.
- Lax: With the "Lax" value, the cookie is sent in cross-site requests that are considered "safe." Safe requests typically include top-level navigation by clicking on links, but not requests made by including resources from external websites (e.g., loading images or scripts).
- None: When the SameSite attribute is set to "None", the cookie is sent in all cross-site requests. However, to use this value, the cookie must also be marked as secure (using the "Secure" attribute) to ensure that it is only sent over secure HTTPS connections.

## Can any server access all cookies in a browser?
In general, No, a server cannot directly access cookies set by other websites or domains. Cookies are specific to the domain that set them, and they are intended to be accessible only by that domain.

However **if SameSite is set to None, then the cookie is accessible by any site.** 


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


