# Sender Policy Framework
SPF stands for "Sender Policy Framework." It is an email authentication method designed to prevent email spoofing, a common technique used by spammers and phishing attackers. SPF allows domain owners to specify which mail servers are authorized to send emails on behalf of their domain.

## DNS Record
The domain owner publishes SPF information in the DNS (Domain Name System) as a specially formatted TXT record. This record contains information about the authorized mail servers for that domain.
## Email Sending Server Check
When an email is received, the recipient's mail server checks the SPF record of the sending domain by querying the DNS. It looks for an SPF record that lists the authorized mail servers.
## Verification
If the sending mail server is listed as an authorized server in the SPF record, the email is considered legitimate. If the server is not listed or the SPF check fails, the email may be treated as suspicious or even rejected.



## Version
The SPF version is declared at the beginning of the SPF record. While there is only one version of SPF (v=spf1), including it is required.
```
v=spf1
```

## Mechanisms
Mechanisms are the components of an SPF record that specify the rules for determining whether an email is legitimate based on the sending server's identity. Common mechanisms include:

all: Defines the default action to be taken if no other mechanism matches. It can be set to +all (allow), -all (reject), or ~all (soft fail, treat with suspicion).
```
v=spf1 -all
```

ip4 and ip6: Specifies specific IPv4 or IPv6 addresses allowed to send emails for the domain.
```
v=spf1 ip4:192.168.1.1 ip6:2001:db8::1 -all
```

a and mx: Authorizes the domain's A or MX records to send emails.
```
v=spf1 a mx -all
```

include: Allows delegation of SPF policy to another domain. The included domain's SPF policy is also considered.
```
v=spf1 include:example.com -all
```

ptr: Validates the client's hostname against a reverse DNS entry.
```
v=spf1 ptr -all
```

exists: Checks for the existence of a specified domain.
```
v=spf1 exists:example.com -all
```

## Modifiers
Modifiers provide additional instructions for SPF processing. Common modifiers include:

redirect: Specifies another domain to inherit the SPF policy.
```
v=spf1 redirect=example.net
```
exp: Provides a URL where an explanation of the sender's policy can be found.
```
v=spf1 exp=spf.example.com
```
