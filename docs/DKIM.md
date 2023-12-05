# DomainKeys Identified Mail (DKIM)
It is an email authentication method designed to verify the authenticity and integrity of email messages. DKIM allows the sender of an email to digitally sign the message, and the recipient can then verify the signature using the sender's public key published in the DNS (Domain Name System).

## Message Signing
When an email is sent, the sending mail server uses a private key to generate a digital signature for the email message. This signature is typically added to the email header as a DKIM-Signature field.

## DNS Record Publication
The sender publishes a public key in the DNS as a DKIM record. This public key can be used by the recipient to verify the authenticity of the digital signature.
## Verification
When the recipient's mail server receives the email, it retrieves the sender's public key from the DNS using the information in the DKIM-Signature field. The server then uses this key to verify the digital signature. If the signature is valid, it indicates that the email has not been tampered with during transit, and it originated from the purported sender.


## Benefits

- **Authentication**: It helps verify that the sender of an email is legitimate and has control over the sending domain.
- **Integrity**: It ensures that the email content has not been altered during transit.
- **Non-repudiation**: It provides a level of non-repudiation, meaning that the sender cannot deny sending the email once it has been signed.
- **Anti-Phishing**: DKIM helps combat phishing attacks by allowing recipients to verify the authenticity of the sender.


## Setup
Setting up DKIM involves a series of steps, including generating a DKIM key pair, publishing the public key in your domain's DNS records, and configuring your email server to sign outgoing messages with the private key. Here's a general guide on how to set up DKIM:

### Step 1: Generate DKIM Key Pair
- Generate a Key Pair:
  Use a tool provided by your email server software or a third-party tool to generate a DKIM key pair, which consists of a private key and a corresponding public key.
- Secure the Private Key:
  The private key must be kept secure, as it is used to sign outgoing emails. Store it in a safe location with restricted access.

### Step 2: Publish DKIM Public Key in DNS
- Publish DNS Record:
  Add a DKIM TXT record to your domain's DNS settings. The TXT record includes the public key and other DKIM-related information.
  Example DNS TXT record:
  ```
  default._domainkey IN TXT "v=DKIM1; k=rsa; p=MIGfMA0GCSqGSIb3DQE..."
  ```
  Note: The selector (in this case, "default") is a label that helps identify the specific DKIM key to use.
### Step 3: Configure Email Server
- Enable DKIM Signing:
  Configure your email server software to sign outgoing messages with the private key. Consult the documentation of your email server software for specific instructions.

- Specify Selector and Key Location:
  In your email server settings, specify the DKIM selector and the location of the private key file.
  ```
  DKIM Selector: default
  DKIM Private Key: /path/to/private/key.pem
  ```
- Test DKIM Setup:
  Send a test email and check the email headers to ensure that the DKIM-Signature field is present and correctly signed.
### Step 4: Monitor and Maintain
- Monitor DKIM Performance:
  Regularly monitor your email server logs and DKIM verification status to ensure proper functioning.

- Key Rotation:
  Consider rotating your DKIM keys periodically for enhanced security. Update the DNS TXT record with the new public key.
