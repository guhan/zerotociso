# Kerberos
Kerberos is a network authentication protocol and system that provides secure authentication for users and services over a non-secure network, such as the internet. It was developed by MIT (Massachusetts Institute of Technology) and has become a widely used authentication protocol in various computing environments, including Microsoft Windows Active Directory domains.

Kerberos is designed to address the problem of secure authentication in a networked environment where sensitive information, such as passwords, should not be transmitted over the network in plaintext. It achieves this goal through the following key principles:

## Authentication
Kerberos provides strong mutual authentication between a user and a service. This means that both parties verify each other's identity before proceeding with any communication.

## Single Sign-On (SSO) 
Once a user has authenticated with the Kerberos authentication server, they receive a ticket-granting ticket (TGT). This TGT can be used to request service tickets for various services without needing to re-enter their credentials for each service. This leads to a seamless Single Sign-On experience.

## Ticket-Based Authentication
Instead of transmitting passwords over the network, Kerberos uses tickets. When a user authenticates, they receive a TGT, which can be used to request service tickets from the Ticket Granting Server (TGS). These service tickets are presented to services to gain access. The tickets are time-limited and encrypted to ensure security.

## Key Distribution
Kerberos uses symmetric key cryptography to secure communication between the user, the Ticket Granting Server (TGS), and the services. Users and services share secret keys with the authentication server.

## Time Sensitivity
To prevent replay attacks, Kerberos incorporates time-based elements into its tickets and authentication process. Tickets have a limited lifetime, and timestamps are used to validate the freshness of tickets.

## Centralized Authentication Server 
The Kerberos authentication server is a centralized authentication authority responsible for verifying the identities of users and services. It manages user accounts and issues TGTs and service tickets.

## Open Standards
Kerberos is based on open standards and protocols, making it interoperable with various operating systems and applications.

## Common use cases
Kerberos is commonly used in Windows Active Directory environments as the default authentication protocol. However, it is not limited to Windows and is also available on various Unix and Unix-like systems. Additionally, Kerberos can be used in conjunction with other security mechanisms, such as IPsec, to provide end-to-end security for network communication.

