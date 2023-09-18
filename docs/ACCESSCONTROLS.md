# Access Controls

## Types of access controls
- **Preventive Access Control**:
Preventive controls aim to minimize the occurrence of security incidents by putting measures in place to prevent unauthorized access and potential threats. Examples include:
  - Authentication: Verifying the identity of users before granting access.
  - Authorization: Assigning permissions and access rights based on roles and responsibilities.
  - Firewalls: Filtering network traffic to block unauthorized access attempts.
  - Intrusion Prevention Systems (IPS): Monitoring and blocking suspicious network activities.
  - Encryption: Protecting sensitive data by converting it into a secure format that requires a decryption key.
- **Detective Access Control**:
Detective controls focus on identifying security incidents and breaches after they've occurred. They play a crucial role in detecting unauthorized activities and responding to them. Examples include:
  - Intrusion Detection Systems (IDS): Monitoring network traffic and identifying patterns of potential attacks.
  - Log Analysis: Analyzing logs and event data to identify unusual or suspicious activities.
  - Security Information and Event Management (SIEM): Collecting, correlating, and analyzing security-related events to detect threats.
  - User and Entity Behavior Analytics (UEBA): Analyzing user and entity behavior to detect anomalies and potential threats.
- **Corrective Access Control**:
Corrective controls are put in place to mitigate the impact of security incidents and breaches by taking action to rectify the situation. Examples include:
  - Incident Response: Developing and executing plans to respond to security incidents effectively.
  - Patch Management: Applying software patches and updates to fix vulnerabilities.
  - Backup and Recovery: Regularly backing up data and having a recovery plan to restore systems after an incident.
- **Deterrent Access Control**:
Deterrent controls discourage potential attackers from attempting unauthorized access by creating visible and perceived barriers. Examples include:
  - Security Cameras: Placing surveillance cameras in strategic locations to discourage unauthorized activities.
  - Warning Signs: Displaying signs indicating security measures and consequences for unauthorized access.
  - Access Badges: Requiring individuals to visibly wear access badges to indicate authorized personnel.

- **Recovery Access Control**: restore or repair after a security policy violation
- **Directive Access Control**: A
  Attemps to force or encourage a subject to follow a policy. Examples include:
  - Signs
  - Policies
- **Compensating Access Control**: alternative when a primary control can't be used
- **Administrative Access Control**: policies or procedures in an org
- **Logical/Technical Control**: hardware or software mechanisms use to manage access and protect resources
- **Physical Control**: can physically tough these, primarily for physical security

## Evalutating Security Controls
The following frameworks are used to evaluate security controls

### Trusted Computer System Evaluation Criteria (TSSEC) aka Rainbow Series
1980s at the DoD

4 major categoroies
- A: Verfified protection. Highest level
  - development cycle is also considered
- B: Mandatory protection
  - more granularity
  - B1: labeled security
  - B2: Structued position, no covert channels
  - B3: Security domains ie more separation and isolation of unrleated process
- C: Direcretionary protection 
  - basic access control
  - C1: discretionary security protection
  - C2 Controlled access protection (media clensing)
- D: Minimal protection. Evaluated but do not meet requirements to belong in another category

#### Books
- Orange: standalone systems
- Red: Network
- Green: Passwords

#### Why abandoned?
- Not much once access is granted
- Tech evolved fast
- Doesn't address personnel, physical, or procedural policy

### Information Technology Security Evaluation Criteria (ITSEC)
made in EU

- systems are Targets of Evaluation (TOE)
- addresses integrity also
- has no TCB


