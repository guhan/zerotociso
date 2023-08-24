# Domain Name System (DNS)


## Resource Records
These are the different types of Resource Records (RRs):

- A Record (Address Record):
Maps a domain name to an IPv4 address.
- AAAA Record (IPv6 Address Record):
Maps a domain name to an IPv6 address.
- CNAME Record (Canonical Name Record):
Creates an alias for a domain name, redirecting it to another domain's A record. Used for subdomains or when multiple domain names point to the same IP address.
- MX Record (Mail Exchange Record):
Specifies the mail servers responsible for receiving email messages on behalf of a domain.
- TXT Record (Text Record):
Allows you to add arbitrary text to the DNS record, often used for verification, sender policy framework (SPF) configuration, and other purposes.
- PTR Record (Pointer Record):
Used in reverse DNS lookup to map IP addresses to domain names. It's used for reverse DNS resolution.
- SRV Record (Service Record):
Specifies information about available services, such as VoIP, instant messaging, or other services associated with a domain.
- NS Record (Name Server Record):
Specifies the authoritative name servers for a domain.
- SOA Record (Start of Authority Record):
Contains administrative information about the zone, including the primary authoritative name server, the email address of the responsible party, and various timing parameters.
- CAA Record (Certification Authority Authorization):
Specifies which certificate authorities are authorized to issue SSL certificates for a domain.
- NAPTR Record (Naming Authority Pointer):
Used for advanced DNS functions, such as providing information for SIP (Session Initiation Protocol) services.
- DNSKEY Record (DNS Key Record):
Used in DNSSEC (Domain Name System Security Extensions) to store public keys used for signing DNS records.
- DS Record (Delegation Signer):
Also used in DNSSEC, the DS record is used to identify the DNSKEY record of a delegated zone.

## How does a host resolve a DNS query?
When a host (client device or computer) wants to query a DNS (Domain Name System) record to resolve a domain name into an IP address, it goes through a series of steps to complete the process. Here's a simplified overview of the steps a host takes to query a DNS record:

- **Local Cache Check**:
The host first checks its local DNS cache to see if it has recently resolved the same domain name. If the requested record is found in the cache and is still valid (not expired), the host can use the cached IP address without making an external query.
- **Querying the Recursive Resolver**:
If the record is not found in the local cache or has expired, the host contacts its configured DNS recursive resolver (typically provided by the ISP or a third-party DNS service). The host sends a DNS query request to the resolver, providing the domain name it wants to resolve.
  - **Iterative Querying**:
The recursive resolver receives the query and begins the process of resolving the domain name. It might have the record cached from previous queries, in which case it can return the IP address directly to the host. If not, the resolver initiates an iterative query process.
- **Root Name Server Query**:
If the recursive resolver doesn't have the requested record, it queries one of the root name servers. The root name servers provide information about the top-level domain (TLD) servers responsible for specific TLDs (.com, .org, .net, etc.).
  - **TLD Name Server Query**:
The root name server provides a referral to the TLD name server responsible for the domain's TLD (e.g., .com). The recursive resolver then queries the TLD name server.
  - **Authoritative Name Server Query**:
The TLD name server provides a referral to the authoritative name server responsible for the specific domain name being queried (e.g., ns1.example.com). The recursive resolver queries the authoritative name server.
  - **Record Response**:
The authoritative name server responds to the recursive resolver with the requested DNS record, such as an IP address associated with the domain name.
- **Recursive Resolver Response**:
The recursive resolver receives the record from the authoritative name server and caches it for future use. It then sends the response back to the original host that made the query.
- **Host Response**:
The host receives the IP address from the recursive resolver. It can then use this IP address to establish a connection to the desired server or resource associated with the domain name.

## What is DNS Cache Poisoning?
DNS cache poisoning occurs when an attacker manipulates the DNS resolution process to redirect users to malicious websites or intercept their communications.

## What is DNSSEC?
Here's a simplified overview of how DNSSEC works:
- Signing: The owner of a domain generates a pair of cryptographic keys—a private key and a corresponding public key. The private key is kept secure, while the public key is published in the DNS records for that domain.

- Chain of Trust: The top-level domain (TLD) responsible for the domain (e.g., .com) signs the DNSKEY records using its private key. This creates a chain of trust where each level of the domain hierarchy signs the keys of the next level.
Validation: When a client queries a DNSSEC-enabled domain, it requests the DNSKEY records to retrieve the public key. It then uses the public key to verify the digital signatures of the other DNS records received.


- Secure Responses: If the DNS responses pass the signature verification, the client can trust that the responses are authentic and haven't been tampered with.
