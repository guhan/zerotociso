## DNS

## What is DNS Cache Poisoning?
DNS cache poisoning occurs when an attacker manipulates the DNS resolution process to redirect users to malicious websites or intercept their communications.

## What is DNSSEC?
Here's a simplified overview of how DNSSEC works:
- Signing: The owner of a domain generates a pair of cryptographic keys—a private key and a corresponding public key. The private key is kept secure, while the public key is published in the DNS records for that domain.

- Chain of Trust: The top-level domain (TLD) responsible for the domain (e.g., .com) signs the DNSKEY records using its private key. This creates a chain of trust where each level of the domain hierarchy signs the keys of the next level.
Validation: When a client queries a DNSSEC-enabled domain, it requests the DNSKEY records to retrieve the public key. It then uses the public key to verify the digital signatures of the other DNS records received.


- Secure Responses: If the DNS responses pass the signature verification, the client can trust that the responses are authentic and haven't been tampered with.
