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


## What is DNS Cache Poisoning?
DNS cache poisoning occurs when an attacker manipulates the DNS resolution process to redirect users to malicious websites or intercept their communications.

## What is DNSSEC?
Here's a simplified overview of how DNSSEC works:
- Signing: The owner of a domain generates a pair of cryptographic keys—a private key and a corresponding public key. The private key is kept secure, while the public key is published in the DNS records for that domain.

- Chain of Trust: The top-level domain (TLD) responsible for the domain (e.g., .com) signs the DNSKEY records using its private key. This creates a chain of trust where each level of the domain hierarchy signs the keys of the next level.
Validation: When a client queries a DNSSEC-enabled domain, it requests the DNSKEY records to retrieve the public key. It then uses the public key to verify the digital signatures of the other DNS records received.


- Secure Responses: If the DNS responses pass the signature verification, the client can trust that the responses are authentic and haven't been tampered with.
