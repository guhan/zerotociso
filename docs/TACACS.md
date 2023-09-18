# TACACS
Terminal Access Controller Access Control System, is a network security protocol that provides centralized authentication, authorization, and accounting (AAA) services for managing user access to network devices and resources. TACACS is primarily used in network infrastructure devices like routers, switches, and network access servers.

TACACS is often used in conjunction with RADIUS (Remote Authentication Dial-In User Service) but serves a similar purpose with some key differences:

## Authentication
TACACS provides authentication services by verifying the credentials (usually username and password) of users trying to access network devices. It allows for separate authentication databases for different services, enabling more granular control over access.
## Authorization
TACACS also handles authorization, which determines what actions or commands a user is allowed to perform after authentication. This authorization is often based on user roles, privileges, or policies.
## Accounting
TACACS records accounting information about user activities, such as logins, logouts, and commands executed. This data is essential for auditing, monitoring, and tracking user actions on network devices.
## Packet Types
TACACS uses separate packet types for authentication, authorization, and accounting. This separation provides more flexibility and control over the AAA process.
## Encryption
TACACS+ (an improved version of TACACS) encrypts the entire authentication and authorization process, including the username and password. This enhances security and privacy compared to the original TACACS protocol.
## Vendor-Specific Attributes
TACACS+ allows for vendor-specific attributes in authorization requests, enabling network administrators to customize the authorization process based on device-specific requirements.
## Shared Secrets
Like RADIUS, TACACS uses shared secrets (keys) between the client (network device) and the TACACS server to secure communications.
