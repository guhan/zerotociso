# Public Key Infrastructure (PKI)
- Digital certificates provide nonrepudiation, they are essentially endorsed copies of an individuals public key. 
- Certificate Authorities (CAs): neutral organizations that offer notarization services for digital certificates
- Relies on a heirarchy of trust relationships
- Registration Authorities (RAs): assist CAs with Know Your Custoemr (KYC)

### Lifecycle of Certificates
**Enrollment**
- prove identity to CA
- provide public key
- CA creates an X.509 cert and copy of your public key
- CA signs the certificate with CA's private key
- Now you can distribute the cert

**Verification**
- You check a cert you get by using the CA's public key
- Check that is not revoked using a Certificate Revocation List or Online Certificate Status Protocol (OCSP)
- Examine the certificate contents

**Revocation**
- Cert was compromised, errorneously issued, details changed
