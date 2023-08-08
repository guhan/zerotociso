# General Security Information

_Security can be expensive, but is most often less costly than the absence of security._

## Key Concepts
- Abstraction: Classify objects for efficiency
- Authorization to Operate (ATO): meeting all regulation so business/entity can operate
- Business case: argument or position that defines a need to make a decision or take some sort of action
- CISO: Chief Information Security Officer
- CSO: Chief Security Officer (interchangeable with CISO)
- Data Hiding: Hide data from access
- Due Care: reasonable care is taken to protect the interests of the organization
- Due Diligence: practicing the activities that maintain due care
- Encryption: Intentionally hiding the meaning of something from intended recipients
- Layering: Defense in depth, using multiple controls so if one fails the others will still work
- Managed Detection and Response (MDR): MDR refers to a cybersecurity service that provides continuous monitoring, threat detection, incident response, and remediation for organizations. MDR providers use advanced tools, technologies, and expertise to detect and respond to security threats and breaches in real-time.
- [Security Policies](/docs/SECURITYPOLICIES.md): Used to assign resopnsibilities, define roles, specify audit requirements, outline enforcement processes, indicate compliance requirements, and define acceptable risks.
- Security Governance: collection of practices related to supporting, defining, and directing the security efforts of an organization
- Security Governance: implementation of a security solution and management method are tightly interconnected
- Security through obscurity: Intentionally hide something and hope it doesn't get found
- Software Composition Analysis (SCA): SCA refers to the process of analyzing software components, libraries, and dependencies used in a software application. It helps identify and manage third-party components, assess their security vulnerabilities, and ensure compliance with licensing requirements.


## What is the CIA Triad?

### C - confidentiality 
Measures used to protect the secrecy of data.
- Need confidentiality in storage, in process, and in transit
- achieved through
  - encryption
  - access controls
  - strong authentication mechanisms
  - secure communication channels.

Related concepts: 
- sensivity: could exposure of this information cause harm
- discretion: operator can control disclosure to minimize harm
- criticality: how mission critical is this information
- concealment: hiding or preventing disclosure
- secrecy: act of keeping something secret
- privacy: keeping personally identifiable information confidential/secret
- seclusion: store something in an out the way location
- isolation: keep things separate 


### I - Integrity 
Protecting the reliability and correctness of data

Techniques that help protect against data tampering or unauthorized changes are:
- hashing
- digital signatures
- checksums
- access controls

Related concepts: 
- accuracy: being correct and precise
- truthfulness: being a true reflection of reality
- authenticity: being genuine
- validity: being factually or logically sound
- **nonrepudiation**: not being able to deny performing an action
- accountability: being responsible for the results
- responsibility: being in charge or in control over someone/something
- completeness: has all necessary parts
- comprehensiveness: complete in scope


### A - Availability 
Authorized users are granted timely and uninterrupted access

Availability measures include:
- redundancy
- fault tolerance
- backup systems
- disaster recovery planning
- robust network and system design.

Related concepts: 
- usability: easy to use
- accessibility: widest range of subjects can interact with a resource
- timeliness: being on time

## AAA Services
Five elements are
- Identification: subject must provide an id, which can be public
- Authentication: provide additional information to validate identity
  - authentication factors are usually private
- Authorization: granting the subject the desired access
- Auditing: subjects actions are tracked (or logged)
- Accounting/Accountability: subjects are accountable for their actions, you can accurately map identity to the subject



## Types of Security Controls
### Administrative Controls:
- Policies and Procedures: Rules and guidelines that govern how security is implemented and enforced within an organization.
- Security Awareness Training: Educating employees about security best practices and potential risks to promote a security-conscious culture.
- Risk Management: Identifying, assessing, and mitigating risks to reduce potential security threats.
### Physical Controls:
- Perimeter Security: Physical barriers, fences, gates, and security guards to control access to buildings or facilities.
- Surveillance: Use of security cameras and monitoring systems to deter and detect unauthorized activities.
- Environmental Controls: Fire suppression systems, temperature control, and humidity control to safeguard hardware and equipment.
### Technical Controls:
- Access Control: Restricting access to resources and data based on user authentication and authorization.
- Encryption: Protecting data by encoding it so that only authorized parties can decrypt and read it.
- Firewalls: Network security devices that filter and control incoming and outgoing traffic based on defined rules.
- Intrusion Detection/Prevention Systems (IDS/IPS): Monitoring and responding to suspicious activities on networks.
- Antivirus/Antimalware Software: Scanning and removing malicious software and files to prevent infections.
### Detective Controls:
- Log Monitoring and Analysis: Reviewing system logs and event data to identify potential security incidents.
- Security Audits: Conducting periodic assessments to identify vulnerabilities and security weaknesses.
### Corrective Controls:
Put in place after an incident has occured

- Incident Response: A planned approach to addressing and managing security incidents when they occur.
- Patch Management: Regularly updating software and systems to fix known vulnerabilities.
### Compensating Controls:
- Alternate measures put in place when primary controls cannot be implemented to the fullest extent.
### Deterrent Controls:
- Measures designed to discourage potential attackers, such as warning signs, security cameras, or visible security personnel.
### Recovery Controls:
- Strategies and plans to restore systems and operations after a security incident or disaster.


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


## What is a Common Weakness Enumerations (CWE)?

Common Weakness Enumeration (CWE) is a community-developed list of common software weaknesses and vulnerabilities. 
CWE is maintained by the MITRE Corporation and is widely used in the field of software security. 



