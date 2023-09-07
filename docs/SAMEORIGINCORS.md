# Same Origin and CORS

## What is the same-origin policy?

An origin is a combination of the protocol, domain, and port number of a web page's URL

The Same origin policy (SOP) aims to prevent malicious scripts from accessing or manipulating data from different origins, thereby protecting user privacy and security.
According to the Same Origin Policy:

- Origin Restriction: Web content, such as JavaScript, HTML, and XMLHTTPRequests, can only interact with resources (e.g., scripts, cookies, or data) from the same origin. The origin includes the same protocol (e.g., HTTP or HTTPS), domain (e.g., example.com), and port number (e.g., 80 for HTTP, 443 for HTTPS).

**important to note that the SOP is enforced by web browsers and can be bypassed through various vulnerabilities or misconfigurations**

- Use Relative URLs
```Set header Access-Control-Allow-Origin: <origin>```

## Cross-Origin Resource Sharing (CORS)
CORS is a mechanism that allows servers to specify which origins are permitted to access their resources. It includes HTTP headers that the server sends in its response to inform the browser about cross-origin permissions.

  - Access-Control-Allow-Origin: https://example.com, https://anotherdomain.com
  - Access-Control-Allow-Methods: Specifies the HTTP methods (e.g., GET, POST, PUT, DELETE) that are allowed for cross-origin requests.
  - Access-Control-Allow-Headers: Specifies the additional HTTP headers (e.g., Authorization, Content-Type) that are allowed for cross-origin requests.
  - Access-Control-Allow-Credentials: Indicates whether the server allows credentials (such as cookies or HTTP authentication) to be included in cross-origin requests. This header is set to true or false.
  - Access-Control-Max-Age: Specifies the maximum duration (in seconds) for which the preflight response (OPTIONS request) can be cached.
