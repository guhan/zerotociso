# HTTP Strict Transport Security

## What is HSTS?

HTTP Strict Transport Security. It is a security mechanism implemented in web browsers and web servers to enforce the use of secure connections over HTTPS (HTTP over SSL/TLS) 

_Basically force HTTPS_

- **Initial Connection**: When a client (web browser) makes the initial connection to a website that supports HSTS, the server responds with a special HTTP header called the Strict-Transport-Security header.
- **HSTS Header:** The Strict-Transport-Security header includes a policy directive with a specified duration. For example:
```Strict-Transport-Security: max-age=31536000```

- **HSTS Preloading**: Websites can also opt to be included in the HSTS preload list maintained by web browsers. This list is hardcoded into the browser, and websites included in the list are always accessed via HTTPS, even for the first visit
