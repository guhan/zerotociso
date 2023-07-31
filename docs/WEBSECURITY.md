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
