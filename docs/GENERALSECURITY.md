# General Security Information

## What is the CIA Triad?

### C - confidentiality 
Confidentiality is often achieved through encryption, access controls, strong authentication mechanisms, and secure communication channels.

### I - Integrity 
Techniques such as hashing, digital signatures, checksums, and access controls help protect against data tampering or unauthorized changes.

### A - Availability 
Availability measures include redundancy, fault tolerance, backup systems, disaster recovery planning, and robust network and system design.

## How do you secure your home network?
- Educate family on phishing, wifi networks and secure passwords
- Patch network equipment regularly
- Use strong wifi encryption 
- WPA2 (Wi-Fi Protected Access 2) 
  - WPA2-Personal (WPA2-PSK): Also known as WPA2-Pre-Shared Key, this mode requires a passphrase or pre-shared key (PSK) to access the Wi-Fi network. The passphrase is used to generate the encryption key. It is important to use a strong and unique passphrase with a combination of upper and lower case letters, numbers, and special characters.
  - WPA2-Enterprise: This mode uses a more robust security mechanism called 802.1X authentication, typically involving a RADIUS (Remote Authentication Dial-In User Service) server. 
- WPA3 (Wi-Fi Protected Access 3).
  - Stronger Encryption: WPA3 uses the more secure and advanced encryption algorithm, such as the 256-bit Galois/Counter Mode Protocol (GCMP-256), providing stronger encryption for network communications.
  - Individualized Data Encryption: WPA3 enables individual data encryption, which means that each device connected to the network has its own encryption key. This helps protect against attacks where an attacker intercepts and decrypts the traffic of other devices on the network.
  - Protection Against Brute-Force Attacks: WPA3 includes mechanisms to prevent offline brute-force attacks on the Wi-Fi network passphrase, making it more difficult for attackers to guess or crack the passphrase.
- Disable remote management of network equipment
- Set a secure root password for network equipment 
- Use strong passwords and MFA
- Use a password manager to remember passwords vs a sheet of paper
- Setup a guest network (network segmentation) and frequently change the password
- Backup all systems (time machine/hard drives) or iCloud
- Disable unnecessary services

## What techniques can be used to prevent a brute-force login attack?
- Limit failed login attempts by blocking IP or locking account
- Use a captcha
- Don’t disclose valid accounts 
- IP whitelisting/blacklists
- WAF
- Monitoring and alerting
- Strong password policy

## How do you ensure a server is secure?
- Install only needed software
- Use service accounts and not root
- Setup automatic patches
- Turn off unneeded services
- Install a firewall (iptables)
- Setup user accounts 
- Setup a lock screen
- Lock the BIOS with a password
- Setup hard disk encryption
- Setup monitoring and logging
- Setup Backups
- Use principle of least privilege


## What is the difference between HIDS and NIDS?
- HIDS is a host based intrusion detection system. It scans a hosts files and looks at authentication attempts and logs to the local system. 

- NIDS is a network based intrusion detection system. It scans network traffic from select points on the network

## What is the difference between IDS and IPS?
IDS is an intrusion detection system and IPS is an intrusion protection system, the IPS will detect and actively protect against attacks





