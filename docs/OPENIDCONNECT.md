# OpenID Connect (OIDC)
OpenID Connect (OIDC) is an identity layer built on top of the OAuth 2.0 authorization framework. It is an open standard and protocol designed to facilitate secure authentication and authorization for web and mobile applications. OIDC provides a standardized way for users to log in to applications using their existing accounts with identity providers, such as social media platforms or identity management systems.

## Identity Provider (IdP)
An identity provider is a service that authenticates users and provides information about their identity. Common IdPs include Google, Facebook, Microsoft Azure AD, and dedicated identity management systems.

## Authentication
OIDC enables user authentication by redirecting users to an IdP's login page. After successful authentication, the IdP sends an ID token to the application, which contains information about the user, including their unique identifier (sub), name (name), and email address (email).

## Authorization
OIDC extends OAuth 2.0's authorization framework to provide user identity information in addition to access tokens. This means that applications can request both user consent and authentication in a single flow.

## ID Tokens
ID tokens are JWTs (JSON Web Tokens) that contain information about the authenticated user. They are signed and optionally encrypted to ensure their integrity and confidentiality.

## Access Tokens
Access tokens, which are also a part of the OIDC flow, can be used to access protected resources on behalf of the user. They are typically short-lived and represent the user's authorization to access specific resources.

## Scopes
OIDC introduces new scopes that allow applications to request specific identity-related information about the user, such as their profile or email address.

## Single Sign-On (SSO)
OIDC enables single sign-on, allowing users to log in once to an IdP and then access multiple applications without needing to re-enter their credentials.

## User Info Endpoint
OIDC defines a user info endpoint where applications can retrieve additional user profile information beyond what's included in the ID token.

## Flow Diagram
![OIDC](/images/OIDC.png)
## Discovery
OIDC provides a discovery mechanism that allows applications to dynamically discover the OIDC endpoints and configuration of an IdP, making it easier to integrate with various identity providers.

## Security
OIDC incorporates security features such as token validation, token expiration, and secure communication (e.g., using HTTPS) to protect user identity and data.
