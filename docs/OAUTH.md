# OAUTH

## What is Oauth2?

OAuth 2.0 (Open Authorization 2.0) is an authorization framework that **allows third-party applications to access the resources of a user on a server**, without the need for the user to share their credentials directly with the third party.

The basic flow of OAuth 2.0 involves multiple parties: the resource owner (user), the client application (third-party application), the authorization server, and the resource server.

- Registration: The client application (third-party) must register with the authorization server. During registration, the client is assigned a client ID and client secret, which are unique identifiers used to authenticate the client to the authorization server.

- Authorization Request: When the user wants to grant access to their resources, the client application initiates the OAuth flow by redirecting the user to the authorization server. The client includes its client ID, the requested scope (specific permissions needed), and a redirect URL.

- User Consent: The user is presented with a consent screen by the authorization server. This screen explains what permissions the client application is requesting and asks the user to grant or deny access.

- Authorization Grant: If the user consents, the authorization server generates an authorization grant, typically in the form of an access token or an authorization code. This grant confirms that the user has authorized the client application to access their resources.

- Token Exchange: The client application sends the authorization grant to the authorization server to obtain an access token. This token serves as proof of authentication and is used to access protected resources on the resource server.


- Resource Access: With the access token, the client application can make authorized requests to the resource server on behalf of the user. The resource server validates the access token and grants access to the requested resources if the token is valid and the permissions are sufficient.


- Refresh Tokens (optional): Access tokens typically have a limited lifespan. To extend the session, the client application can use a refresh token (if provided) to obtain a new access token without requiring user interaction.



