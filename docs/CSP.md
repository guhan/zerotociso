# Content Security Policy 

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
