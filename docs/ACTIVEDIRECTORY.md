# Active Directory (AD)
Active Directory (AD) is a directory service and identity management system developed by Microsoft. It is a central component of the Windows operating system and is used by organizations to manage and control access to network resources, including computers, servers, printers, files, and applications. Active Directory provides a centralized repository for storing and managing information about users, groups, devices, and other objects within a networked environment.

## Domain Services
Active Directory Domain Services (AD DS) is the core component of AD. It stores information about network objects, such as users, groups, computers, and organizational units (OUs). AD DS uses a hierarchical structure known as a domain tree, where domains can be grouped into a forest. Each domain has its own security policies, user accounts, and group policies.

![AD DS](/images/ADDS.png)

## Authentication and Authorization
AD provides authentication services, verifying the identity of users and devices trying to access network resources. It also manages authorization, determining what resources each authenticated user or device can access based on permissions and security policies.
## Single Sign-On (SSO)
Active Directory enables Single Sign-On, allowing users to log in once with their AD credentials and gain access to multiple network resources without needing to re-enter their username and password for each resource.
## Group Policy
Group Policy allows administrators to define and enforce security and configuration settings for users and computers in the network. Policies can be applied at the domain, site, or organizational unit level.
## Directory Replication
AD uses directory replication to ensure that data is synchronized across multiple domain controllers (servers that store AD data). This redundancy improves fault tolerance and availability.
## LDAP (Lightweight Directory Access Protocol)
Active Directory supports LDAP, a standardized protocol for accessing and querying directory services. LDAP enables third-party applications and services to interact with AD.
## Kerberos Authentication
AD uses the Kerberos authentication protocol to secure authentication requests and ensure secure communication between clients and domain controllers.
## Trust Relationships
Active Directory allows the establishment of trust relationships between domains in the same forest or even across forests. Trusts enable users from one domain to access resources in another domain.
## Security Groups
AD enables the creation of security groups to manage and assign permissions to resources. Members of security groups inherit the group's permissions, simplifying access control.
## Certificate Services
AD Certificate Services (AD CS) provides a framework for issuing and managing digital certificates, enabling secure communications and authentication in the network.
## Federation Services
AD Federation Services (AD FS) extends identity and access management to external partners, allowing single sign-on and secure access to resources across organizational boundaries.
