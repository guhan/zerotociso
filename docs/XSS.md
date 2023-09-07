# Cross Site Scripting (XSS)

## What is Cross Site Scripting (XSS)?
Allows attackers to inject malicious scripts (referred to as "payloads") into web pages viewed by other users. XSS attacks occur when an application fails to properly sanitize or validate user-supplied input

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

## Real life examples of XSS
- British Airways
  - In 2018, British Airways was attacked by Magecart, a high-profile hacker group famous for credit card skimming attacks. The group exploited an XSS vulnerability in a JavaScript library called Feedify, which was used on the British Airway website. 

  - Attackers modified the script to send customer data to a malicious server, which used a domain name similar to British Airways. The fake server had an SSL certificate, so users believed they were purchasing from a secure server. They succeeded in performing credit card skimming on 380,000 booking transactions before the breach was discovered.

- Fortnite
  - In 2019, the popular multiplayer game experienced an XSS vulnerability that over 200 million users. A retired, unsecured page went unnoticed by Fortnite developers. The page had an XSS vulnerability that allowed attackers to gain unauthorized access to the data of all Fornite users.

  - Attackers could have used XSS, in combination with an insecure single sign on (SSO) vulnerability, to redirect users to a fake login page. This would allow them to steal virtual currency within the game, and record player conversations, as reconnaissance for future attacks. Check Point discovered the attack and notified Fortnite, but it is unknown if the vulnerability was exploited by attackers in the interim.

- eBay
  - In late 2015 and early 2016, eBay had a severe XSS vulnerability. The website used a “url” parameter that redirected users to different pages on the platform, but the value of the parameter was not validated. This allowed attackers to inject malicious code into a page. 

  - The vulnerability enabled attackers to gain full access to eBay seller accounts, sell products at a discount, and steal payment details. It was actively used by attackers to manipulate eBay listings of high value products such as vehicles. eBay eventually remediated the vulnerability, but follow-on attacks continued until 2017.
