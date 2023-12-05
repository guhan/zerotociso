# Certification Authority Authorization (CAA)
A Certification Authority Authorization (CAA) record is used to specify which certificate authorities (CAs) are allowed to issue certificates for a domain.

CAA records allow domain owners to declare which certificate authorities are allowed to issue a certificate for a domain. They also provide a means of indicating notification rules if someone requests a certificate from an unauthorized certificate authority. If no CAA record is present, any CA is allowed to issue a certificate for the domain. If a CAA record is present, only the CAs listed in the record(s) are allowed to issue certificates for that hostname.

CAA records can set policy for the entire domain, or for specific hostnames, and are inherited by subdomains. For example, a CAA record set on example.com also applies to subdomain.example.com.

## CAA record format
CAA records must match the following pattern of:
```
<flags> <tag> <value>
```


## Policies restricting certificate issuance to specific types and CAs
CAA records can control the issuance of single-name certificates, wildcard certificates, or both, though the issue and issuewild tags:

- issue sets a policy for single-name certificate issuance.
- issuewild sets a policy for wildcard and single-name certificate issuance and overrides any issue policy set on the same name.
As many CAA records as needed can be created on the same name to describe any desired set of restrictions for CAs.

## Example
Allow Let’s Encrypt to issue normal certs and Sectigo to issue wildcard and normal certs
```
example.com.  CAA 0 issue "letsencrypt.org"
example.com.  CAA 0 issuewild "sectigo.com"
```
