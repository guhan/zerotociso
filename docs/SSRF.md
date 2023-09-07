# Server Side Request Forgery (SSRF)

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



## How do you prevent SSRF?
- **Input Validation**: Implement proper input validation and sanitization techniques to prevent attackers from manipulating URLs or injecting malicious input.


- **Whitelisting**: Use whitelisting techniques to allow only specific URLs or domains that are trusted and necessary for the application's functionality.


- **Restrict Network Access**: Configure firewalls or security groups to restrict network access and prevent the server from reaching unauthorized internal resources.


- **URL Parsing and Validation**: Implement strict URL parsing and validation routines to ensure that only valid and intended URLs are processed by the server.


- **Least Privilege Principle**: Ensure that the server making requests has the least privilege necessary and only has access to the resources it actually requires.
