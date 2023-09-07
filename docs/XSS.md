# Cross Site Scripting (XSS)

## What is Cross Site Scripting (XSS)?
allows attackers to inject malicious scripts (referred to as "payloads") into web pages viewed by other users. XSS attacks occur when an application fails to properly sanitize or validate user-supplied input

## What are the different types of XSS vulnerabilities?
- **Stored XSS** (Persistent XSS): The injected payload is permanently stored on the target server and is later retrieved and displayed to other users. For example, a malicious script injected into a forum post or a user profile that is displayed to visitors.
- **Reflected XSS** (Non-Persistent XSS): The injected payload is embedded within a URL or a form input, and it is reflected back in the server's response. The attack relies on tricking users into clicking on a specially crafted link that contains the payload, leading to its execution.
  - Reflected XSS vulnerabilities often occur when user input is directly incorporated into HTML templates, URLs, or other dynamic content without proper encoding or validation.

- **DOM-based XSS**: This type of XSS occurs when the payload is processed and executed by the browser's Document Object Model (DOM), rather than by the server. The attack involves manipulating the DOM structure or properties in a way that triggers the execution of the malicious code.

## How to prevent XSS attacks? 
- **Input Sanitization**: Ensure that all user-supplied input is properly validated, encoded, or sanitized before being displayed on a web page to prevent the execution of malicious code.
- **Output Encoding**: Use proper output encoding techniques to ensure that user-supplied data is displayed as plain text or as escaped HTML, preventing any interpretation of injected code.
- [**Content Security Policy (CSP)**](CSP.md): Implement a Content Security Policy that restricts the types of content that can be loaded and executed on a web page, effectively reducing the impact of XSS attacks.
- **Security Testing**: Regularly perform security testing, including vulnerability scanning and penetration testing, to identify and address any XSS vulnerabilities in your web applications.
