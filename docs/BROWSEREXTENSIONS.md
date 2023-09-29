# Browser Extensions
A browser extension is a small software program or add-on that extends the functionality of a web browser. These extensions are typically designed to enhance the browsing experience, add new features, or modify the behavior of the browser in some way.

Securing browser extensions requires several layers on controls to ensure malicious activity can be minimized when using the extension. 
Broadly the areas to focus the conrols are the following: 
- Deployment and Configuration
- Communication to/from extension
- Data Processing in the extension

## Deployment and Configuration
#### Protect developer accounts
Extension code is uploaded and updated through Google accounts. If developers' accounts are compromised, an attacker could push malicious code directly to all users. Protect these accounts by by enabling two-factor authentication , preferably with a security key.
####  Keep groups selective
If using group publishing, keep the group confined to trusted developers. Do not accept membership requests from unknown persons.
#### Request minimal permissions
The Chrome browser limits an extension's access to privileges that have been explicitly requested in the manifest. Extensions should minimize their permissions by only registering APIs and websites they depend on.
Limiting an extension's privileges limits what a potential attacker can exploit.
## Limit manifest fields
Including unnecessary keys and permissions in the manifest creates vulnerabilities and makes an extension more visible. Limit manifest fields to those the extension relies on.


## Communication to/from Extension
#### Never use HTTP
When requesting or sending data, avoid an HTTP connection. Assume that any HTTP connections will have eavesdroppers or contain modifications. HTTPS should always be preferred, as it has built-in security circumventing most man-in-the-middle attacks.
#### Cross-origin fetch()
An extension can only use fetch() and XMLHttpRequest() to get resources from the extension and from domains specified in the permissions. Note that calls to both are intercepted by the fetch handler in the service worker.
```
{
  "name": "Very Secure Extension",
  "version": "1.0",
  "description": "Example of a Secure Extension",
  "host_permissions": [
    "https://developer.chrome.com/*",
    "https://*.google.com/*"
  ],
  "manifest_version": 3
}
```
This extension in the sample above requests access to anything on developer.chrome.com and subdomains of Google by listing "https://developer.chrome.com/*" and "https://*.google.com/*" in the permissions. If the extension were compromised, it would still only have permission to interact with websites that meet the match pattern. The attacker would only have limited ability to access "https://user_bank_info.com", or interact with "https://malicious_website.com".
#### Externally connectable
Use the "externally_connectable" field to declare which external extensions and web pages the extension will exchange information with. Restrict who the extension can externally connect with to trusted sources.
```
{
  "name": "Super Safe Extension",
  "externally_connectable": {
    "ids": [
      "iamafriendlyextensionhereisdatas"
    ],
    "matches": [
      "https://developer.chrome.com/*",
      "https://*.google.com/*"
    ],
    "accepts_tls_channel_id": false
  },
  ...
}
```
#### Web-accessible resources
Making resources accessible by the web, under the "web_accessible_resources" will make an extension detectable by websites and attackers.
```
{
  ...
  "web_accessible_resources": [
    {
      "resources": [ "test1.png", "test2.png" ],
      "matches": [ "https://web-accessible-resources-1.glitch.me/*" ]
    }
  ]
  ...
}
```
The more web accessible resources available, the more avenues a potential attacker can exploit. Keep these files to a minimum.

#### Include an explicit content security policy
Include a content security policy for the extension in the manifest to prevent cross-site scripting attacks. If the extension only loads resources from itself register the following:
```
{
  "name": "Very Secure Extension",
  "version": "1.0",
  "description": "Example of a Secure Extension",
   "content_security_policy": {
    "extension_pages": "default-src 'self'"
  },
  "manifest_version": 3
}
```
If the extension needs to use web assembly, or increase the restrictions on sandboxed pages, they can be added:
```
{
  "name": "Very Secure Extension",
  "version": "1.0",
  "description": "Example of a Secure Extension",
   "content_security_policy": {
    "extension_pages": "script-src 'self' 'wasm-unsafe-eval'; object-src 'self';",
    "sandboxed_pages":"script-src 'self' 'wasm-unsafe-eval'; object-src 'self';"
  },

  "manifest_version": 3
}
```


## Data processing in the extension
#### Avoid document.write() and innerHTML
While it may be simpler to dynamically create HTML elements with document.write() and innerHTML, it leaves the extension, and web pages the extension depends on, open to attackers inserting malicious scripts. Instead, manually create DOM nodes and use innerText to insert dynamic content.
```
function constructDOM() {
  let newTitle = document.createElement('h1');
  newTitle.innerText = host;
  document.appendChild(newTitle);
}
```
#### Use content scripts carefully
While content scripts live in an isolated world, they are not immune from attacks:
- Content scripts are the only part of an extension that interacts directly with the web page. Because of this, hostile web pages may manipulate parts of the DOM the content script depends on, or exploit surprising web standard behavior, such as named items.
- To interact with DOM of web pages, content scripts need to execute in the same renderer process as the web page. This makes content scripts vulnerable to leaking data via side channel attacks (e.g., Spectre), and to being taken over by an attacker if a malicious web page compromises the renderer process.
- Operations using sensitive data (such as a user's private information) or Chrome APIs with access to the browser's functions should be performed in the extensions' service worker. Avoid accidentally exposing extension privileges to content scripts:
- Assume that messages from a content script might have been crafted by an attacker (e.g. validate and sanitize all input and protect your scripts from cross-site scripting).
- Assume any data sent to the content script might leak to the web page. Do not send sensitive data (e.g. secrets from the extension, data from other web origins, browsing history) to content scripts.
- Limit the scope of privileged actions that can be triggered by content scripts. Do not allow content scripts to trigger requests to arbitrary URLs or pass arbitrary arguments to extension APIs (e.g., do not allow passing arbitrary URLs to fetch() or chrome.tabs.create() methods).

#### Register and sanitize inputs
Safeguard an extension from malicious scripts by limiting listeners to only what the extension is expecting, validating the senders of incoming data, and sanitizing all inputs.
An extension should only register for runtime.onMessageExternal, if it is expecting communication from an external website or extension. Always validate that the sender matches a trusted source.
```
// The ID of an external extension
const kFriendlyExtensionId = "iamafriendlyextensionhereisdatas";

chrome.runtime.onMessageExternal.addListener(
  function(request, sender, sendResponse) {
    if (sender.id === kFriendlyExtensionId)
      doSomething();
});
```
Even messages via runtime.onMessage event from the extension itself should be scrutinized to ensure the MessageSender is not from a compromised content script.
```
chrome.runtime.onMessage.addListener(function(request, sender, sendResponse) {
  if (request.allowedAction)
    console.log("This is an allowed action.");
});
```
