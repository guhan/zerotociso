# Certificate Transparency Project
The [Certificate Transparency (CT) project](https://certificate.transparency.dev) is an open framework for monitoring and auditing the digital certificates issued by Certificate Authorities (CAs). Digital certificates are crucial for securing online communication by enabling the use of encryption protocols like HTTPS. However, the system is vulnerable to various attacks, such as the issuance of fraudulent certificates.

Certificate Transparency was proposed by Google in 2011 as a way to address these vulnerabilities and enhance the security of the Public Key Infrastructure (PKI). The primary goal of CT is to provide an open and verifiable log of all issued certificates, allowing domain owners and users to detect and respond to unauthorized or fraudulent certificate issuances promptly.

## Certificate Logging
CAs are required to submit all issued certificates to public, append-only logs. These logs are maintained by independent entities and are publicly accessible.
## Auditing and Monitoring
Domain owners and other concerned parties can monitor these logs for certificates issued for their domains. They can set up monitoring systems to detect any suspicious or unauthorized certificates.
## Inclusion Proof
Certificate Transparency also introduces the concept of "inclusion proofs." These are cryptographic proofs that a certificate has been logged in one or more public logs. Inclusion proofs can be used to demonstrate that a certificate has been properly recorded in the logs.
## Certificate Auditing Tools
Various tools and services have been developed to help users and organizations audit and monitor certificates effectively. These tools can check whether certificates for specific domains are properly logged in the Certificate Transparency logs.
