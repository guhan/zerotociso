# Lightweight Directory Access Protocol (LDAP)
LDAP (Lightweight Directory Access Protocol) is a protocol used for accessing and managing directory information services. LDAP is commonly used for centralized authentication, authorization, and directory services in various networked environments, including corporate networks, universities, and the internet. 

## LDAP Directory Structure
- LDAP organizes data in a hierarchical directory structure, often referred to as a directory tree or directory information tree (DIT).
- The top-level entry in the LDAP directory is called the "root" or "base DN" (Distinguished Name). All other entries are organized hierarchically beneath it.

## LDAP Entries:
- Each entry in an LDAP directory is uniquely identified by a Distinguished Name (DN), which is composed of a series of relative distinguished names (RDNs).
- An entry can represent various types of information, such as users, groups, devices, and organizational units (OUs).
- Attributes: Entries have attributes that hold specific pieces of information. Attributes can be single-valued (e.g., "cn" for common name) or multi-valued (e.g., "mail" for email addresses).
Example DN: ```cn=John Doe,ou=Users,dc=example,dc=com```

## LDAP Protocol:
- LDAP uses a client-server model. LDAP clients send requests to LDAP servers to retrieve, add, modify, or delete directory information.
- LDAP operates over TCP/IP, typically using port 389 (LDAP) or port 636 (LDAPS, LDAP over TLS/SSL for secure communication).

## Authentication and Authorization:
- LDAP can be used for authentication by clients to verify user identities. Users provide their credentials (e.g., username and password), and the LDAP server checks these against its directory entries.
- LDAP can also be used for authorization by specifying access controls and permissions for directory entries.

## LDAP Operations:
- LDAP supports various operations or requests, including:
  - **Bind**: Establishing a connection to the LDAP server, often used for authentication.
  - **Search**: Retrieving directory entries based on specific criteria (e.g., search filters).
  - **Add**: Adding new entries to the directory.
  - **Modify**: Changing attributes within existing entries.
  - **Delete**: Removing entries from the directory.
  - **Compare**: Checking if a specific attribute in an entry matches a provided value.
  - **Modify DN**: Renaming or moving entries within the directory tree.
  - **Extended**: Support for additional, custom operations.

## Search Filters:
- LDAP clients can use search filters to specify the criteria for retrieving directory entries. Filters can be complex and allow for searching based on attributes, attribute values, and logical operators (AND, OR).
Example search filter: (objectClass=person)

## LDAP Security:
- To secure LDAP communications, LDAPS (LDAP over TLS/SSL) is often used. LDAPS encrypts data between the LDAP client and server, ensuring data privacy and integrity.
- LDAP also supports various authentication methods, including simple authentication (username and password), SASL (Simple Authentication and Security Layer) mechanisms, and more.

## LDAP Clients and Servers:
- LDAP clients can be various applications, including email clients, web applications, and operating systems that use LDAP for user authentication and directory services.
- LDAP servers, such as Microsoft Active Directory, OpenLDAP, and Novell eDirectory, store and manage directory information and respond to client requests.
