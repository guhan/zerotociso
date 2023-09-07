# XML Enternal Entity (XXE)

## What is XML External Entity (XXE)?

XML External Entity - similar to SSRF where a server returns sensitive or private information because of a malformed XML request for External Entity

- **XML Parsing**: XML is a widely used data format for exchanging structured information. When an application processes XML input, it typically uses a parser to interpret and extract data from the XML.


- **External Entity**: XML allows for the declaration and referencing of external entities. An external entity is a resource, such as a file or URL, that can be included or referenced within the XML document.


- **Exploitation**: In the case of an XXE vulnerability, an attacker can craft a malicious XML input that includes an external entity reference pointing to a sensitive file or a remote server they control. When the vulnerable application processes the XML, it resolves the external entity, potentially leading to unintended consequences.

## How to prevent XXE vulnerabilities?

- **Input Validation**: Validate and sanitize all user-supplied XML input. Reject or filter out any unexpected or potentially malicious content.
Disable External Entities: Configure the XML parser to disable the processing of external entities or limit their usage to trusted sources only.
- **Use Safe APIs**: Use secure XML parsing libraries or APIs that have built-in protection against XXE vulnerabilities, such as disabling external entity resolution by default.
- **Content-Type Checking**: Validate the Content-Type of incoming XML requests to ensure they match the expected XML format.
- **Least Privilege**: Run the server processes with the least privileges required to mitigate the potential impact of XXE attacks.
