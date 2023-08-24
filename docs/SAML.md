# OASIS Security Assertion Markup Language (SAML)

OASIS Open is a community where experts can advance projects, including open source projects, for cybersecurity, blockchain, IoT, emergency management, cloud computing, and legal data exchange.

SAML is a standard that defines a framework for exchanging security information between online business partners. Developed by the Security Services Technical Committee, SAML is an XML-based framework that supports business communications for user authentication, entitlement, and attribute information. Organizations can apply it to human and machine entities, partner companies, or other enterprise applications. Organizations most often use SAML for web single-sign-on (SSO), attribute-based authorization, and securing web services.

SAML consists of four main components:
1. Assertions: Information that includes authentication, attribute, and authorization decisions
2. Protocols: Request/response protocols that help identity providers manage user requests to resources
3. Bindings: Mappings of request-response message exchanges to standard messaging or communication protocols
4. Profiles: Definitions that show how SAML can be used within a particular application as a way to promote interoperability

## How does SAML work?
SAML, which stands for Security Assertion Markup Language, is an XML-based framework for enabling secure authentication and authorization 
between different parties, such as a user, an identity provider (IdP), and a service provider (SP). It's commonly used for implementing 
Single Sign-On (SSO) solutions in web applications and services.

SAML allows users to access multiple services or applications using a single set of login credentials. Instead of requiring users to 
log in separately to each service, SAML enables them to authenticate once with an identity provider and then access multiple service 
providers without reentering their credentials.

Here's how SAML works:

- **User Access Request**: When a user tries to access a service or application provided by a service provider (SP), the SP redirects 
the user to the identity provider (IdP).
- **Authentication at IdP**: The identity provider (IdP) authenticates the user. This can involve username and password, multi-factor authentication (MFA), or other authentication methods.
- **SAML Assertion**: After successful authentication, the IdP generates a SAML assertion, which is an XML document containing information about the user and their authentication status. The assertion is digitally signed by the IdP to ensure its integrity.
- **Response to SP**: The IdP sends the SAML assertion back to the user's browser, which then forwards it to the service provider (SP).
- **Access Granted**: The service provider (SP) receives the SAML assertion, verifies the digital signature of the IdP, and extracts the user's information and authentication status. If everything checks out, the user is granted access to the service or application without needing to log in again.

Key features and benefits of SAML include:

- **Single Sign-On (SSO)**: Users only need to authenticate once and can access multiple services seamlessly.
- **Security**: SAML uses digital signatures and encryption to ensure the integrity and confidentiality of the authentication and authorization process.
- **Interoperability**: SAML is a widely accepted standard for SSO and works across different platforms and technologies.
- **Centralized Identity Management**: Identity providers (IdPs) centralize user authentication, simplifying user management and access control.
- **Decentralized Architecture**: Different service providers (SPs) can trust a common identity provider, reducing the need for each SP to manage its own authentication.
