# XTACACS
XTACACS, or Extended Terminal Access Controller Access Control System, is a proprietary authentication and authorization protocol developed by Livingston Enterprises (now part of Alcatel-Lucent) for network access control. It is a predecessor to TACACS+ (Terminal Access Controller Access Control System Plus), which is more widely adopted today.

XTACACS provides similar functionality to TACACS in terms of authentication, authorization, and accounting (AAA) services, but it has some differences and limitations compared to TACACS+. Here are some key characteristics of XTACACS:

## Authentication
XTACACS provides user authentication services, typically using a username and password. It verifies the credentials of users trying to access network devices and services.
## Authorization
Like TACACS, XTACACS supports authorization, which determines what actions or commands a user is allowed to perform after authentication. Authorization is often based on user roles, privileges, or policies.
## Accounting
XTACACS records accounting information about user activities, such as logins, logouts, and commands executed. This data is essential for auditing and tracking user actions on network devices.
## Packet Structure
XTACACS uses its own packet structure for communication between network devices (clients) and the XTACACS server. The packet format is different from TACACS and TACACS+.
## Limited Encryption
XTACACS has limited encryption capabilities, and it doesn't encrypt the entire authentication and authorization process. This makes it less secure compared to TACACS+ and RADIUS.
## Vendor-Specific Attributes
Similar to TACACS+, XTACACS allows for vendor-specific attributes in authorization requests, enabling customization of the authorization process.
