# zerotociso
Reference material for those interested in cybersecurity


## Hardware
- [Basic Input/Output System (BIOS)](docs/BIOS.md) 
- [Unified Extentisible Firmware Interface (UEFI)](docs/UEFI.md)
  - [Phlashing](docs/PHLASHING.md)
  - [BrickerBot](https://www.cisa.gov/news-events/ics-alerts/ics-alert-17-102-01a)
- [Central Processing Unit (CPU)](docs/CPU.md)
- Memory
  - [Memory Addressing](docs/MEMORYADDRESSING.md)
  - [Read Only Memory (ROM)](docs/ROM.md)
      - [RAID](docs/RAID.md)
  - [Random Access Memory (RAM)](docs/RAM.md)
- [Embedded Systems](docs/EMBEDDEDSYSTEM.md)
- [Cables](docs/CABLES.md)
- [Repeater](docs/REPEATER.md)
- [Hub](docs/HUB.md)
- [Bridge](docs/BRIDGE.md)
- [Switch](docs/SWITCH.md)
  - [VLAN Hopping](docs/VLANHOPPING.md)
- [Router](docs/ROUTER.md)
- [Forensic Disk Controller](docs/FORENSICDISK.md)


## Networking
- [Basics](docs/NETWORKING.md) 
- [Topologies](docs/NETWORKTOPOLOGIES.md)
- [OSI Model](docs/OSIMODEL.md)
- [Ethernet (802.3)](docs/ETHERNET.md)
- [Point to Point Protocol (PPP)](docs/PPP.md)
- [Frame Relay](docs/FRAMERELAY.md)
- [X.25](docs/X25.md)
- [Layer 2 Forwarding (L2F)](docs/L2F.md)
- [Layer 2 Tunneling Protocol (L2TP)](docs/L2TP.md)
- [Point to Point Tunneling Protocol (PPTP)](docs/PPTP.md)
- [Integrated Services Digital Network (ISDN)](docs/ISDN.md)
- [Internet Protocol (IP)](docs/IP.md)
  - [Dynamic Host Configuration Protocol (DHCP)](docs/DHCP.md)
    - [APIPA](docs/APIPA.md)
  - [Teardrop Attack](docs/TEARDROP.md)
  - [Land Attack](docs/LAND.md)
- [Internet Control Messaging Protocol (ICMP)](docs/ICMP.md)
  - [Ping Flood Attack](docs/PINGFLOOD.md)
  - [Ping of Death Attack](docs/PINGOFDEATH.md)
  - [ICMP Redirect Attack](docs/ICMPREDIRECTATTACK.md)
  - [ICMP Time Exceeded Attack](docs/ICMPTIMEEXCEEDED.md)
  - [ICMP Echo Request Fragmentation Attack](docs/ECHOREQUESTFRAGMENTATION.md)
  - [ICMP Port Unreachable Attack](docs/PORTUNCREACHABLE.md)
  - [Smurf Attack](docs/SMURF.md)
- [Transmission Control Protocol (TCP)](docs/TCP.md)
  - [SYN Flood Attack](docs/SYNFLOOD.md)
  - [SYN Cookies](docs/SYNCOOKIES.md)
  - [Christmas Tree Attack](docs/CHRISTMASTREE.md)
- [User Datagram Protocol (UDP)](docs/UDP.md)
  - [Fraggle Attack](docs/FRAGGLE.md)
- [IPSEC](docs/IPSEC.md)
- [Domain Name Service (DNS)](docs/DNS.md)
  - [Certificate Authority Authorization (CAA)](docs/CAA.md)
- [LAN Technologies](docs/LAN.md)
- [Firewalls](docs/FIREWALLS.md)
- [Email](docs/EMAIL.md)
  - [Sender Policy Framework (SPF)](docs/SPF.md)
  - [Domain Key Idendity Management (DKIM)](docs/DKIM.md)
  - DMARC
- [Voice](docs/VOICE.md)
- [Wireless](docs/WIRELESS.md)
  - [802.11i](docs/80211i.md)
  - Deauthentication Attack
  - Evil Twin Attack
  - Brute Force Attack
- [Bluetooth (802.15)](docs/BLUETOOTH.md) 

## [Operating Systems](docs/OS.md)
  - [US Goverment Security Modes](docs/USSECMODES.md)
  - [Linux](docs/LINUX.md)
    - [Runlevels](docs/RUNLEVELS.md)
    - [Inode](docs/INODE.md)
    - [Filesystem](docs/FILESYSTEM.md)
    - [Extended Attributes](docs/EXTENDEDATTRIBUTES.md)
    - [Signals](docs/SIGNALS.md)
    - [Linux ACL](docs/LINUXACL.md)
    - [Security Enhanced Linux (SELINUX)](docs/SELINUX.md)
    - [App Armor](docs/APPARMOR.md)
  - [Interprocess Communication (IPC)](docs/IPC.md)
    - [System V Semaphores](docs/SYSVSEMAPHORES.md)

## Programming
- [Architecture](docs/ARCHITECTURE.md) 
- [Languages](docs/LANGUAGES.md) 
- [Documentation](docs/DOCUMENTATION.md)
- [Code Repositories](docs/CODEREPOSITORIES.md)
- [Python](docs/PYTHON.md)
- [Serialization](docs/SERIALIZATION.md)
  - [Deserialization Attacks](docs/DESERIALIZATION.md)
- [High Performance Computing](docs/HPC.md)

## Quality Assurance
- [Testing Basics](docs/TESTING.md)
- [International Software Testing Qualifications Board (ISTQB)](docs/ISTQB.md)
- [Fuzzing](docs/FUZZ.md)
- [Static Analysis](docs/SAST.md)
- [Mutation Testing](docs/MUTATIONTESTING.md)

## [Access Controls](docs/ACCESSCONTROLS.md)
  - Frameworks
    - [TSSEC](docs/TSSEC.md)
    - [ITSEC](docs/ITSEC.md)
    - [Common Criteria](docs/ISO15408.md)
  - [Access Control Matrix](docs/ACCESSCONTROLMATRIX.md)
  - [Lattice Based Access Control](docs/LATTICEACCESSCONTROL.md)
  - [Models](docs/ACCESSCONTROLMODELS.md)
    - [Trusted Computing Base (TCB)](docs/TCB.md)
    - [State Machine Model](docs/STATEMACHINE.md)
    - [Information Flow Model](docs/INFORMATIONFLOW.md)
    - [Non-interference Model](docs/NONINTERFERENCE.md)
    - [Take Grant Model](docs/TAKEGRANT.md)
    - [Bell LaPadula Model](docs/BELLLAPADULA.md)
    - [Biba Model](docs/BIBA.md)
    - [Clark Wilson Model](docs/CLARKWILSON.md)
    - [Brewer Nash (Chinese Wall) Model](docs/BREWERNASH.md)
    - [Goguen-Meseguer Model](docs/GOGUEN.md)
    - [Sutherland Model](docs/SUTHERLAND.md)
    - [Graham-Denning Model](docs/GRAHAMDENNING.md)


## Authentication
- [Basics](docs/AUTHENTICATION.md)
- [Passwords](docs/PASSWORDS.md)
- [Password Authentication Protocol (PAP)](docs/PAP.md)
- [Challenge Handshake Authentication Protocol (CHAP)](docs/CHAP.md)
- [Extensible Authentication Protocol (EAP)](docs/EAP.md)
- [Lightweight Extensible Authentication Protocol (LEAP)](docs/LEAP.md)
- [Protected Extensible Authentication Protocol (PEAP)](docs/PEAP.md)
- [802.1x](docs/8021X.md)
- [Single Sign On (SSO)](docs/SSO.md)
  - [Security Assertion Markup Language (SAML)](docs/SAML.md)
  - [Service Provisioning Markup Language (SPML)](docs/SPML.md)
- [Open Authorization (OAuth)](docs/OAUTH.md)
  - [SCIM](docs/SCIM.md)
- [OpenID Connect (OIDC)](docs/OPENIDCONNECT.md)
- [Shibboleth](docs/SHIBBOLETH.md)
- [Biometrics](docs/BIOMETRIC.md)
- [Pluggable Authentication Modules (PAM)](docs/PAM.md)

## Authorization
  - [Basics](docs/AUTHBASICS.md)
  - [Mandatory Access Control (MAC)](docs/MAC.md)
  - [Discretionary Access Control (DAC)](docs/DAC.md)
  - [Rule Based Access Control (RAC)](docs/RAC.md)
  - [Role Based Access Control (RBAC)](docs/RBAC.md)
  - [Task Based Access Control (TBAC)](docs/TBAC.md)
  - [Attribute Based Access Control (ABAC)](docs/ABAC.md)
  - [Network Access Control (NAC)](docs/NAC.md)
  - [Open Policy Agent (OPA)/REGO](docs/OPA.md)

## [Authentication, Authorization, and Accounting (AAA)](docs/AAA.md)
- [RADIUS](docs/RADIUS.md)
- [TACACS+](docs/TACACS.md)
- [XTACACS](docs/XTACACS.md)


## [Cryptography](docs/CRYPTOGRAPHY.md)
  - [Data Encryption Standard (DES)](docs/DES.md)
  - [Triple DES (3DES)](docs/3DES.md)
  - [Hashing](docs/HASHING.md)
  - [Digital Signatures](docs/DIGITALSIGNATURES.md)
  - [Public Key Infrastructure (PKI)](docs/PKI.md)
    - [Certificate Transparency Project](docs/CERTTRANS.md)
  - [Hardware](docs/CRYPTOHARDWARE.md)
  - [Email](docs/CRYPTOEMAIL.md)
  - [Side Channel Attacks](docs/SIDECHANNEL.md)
  - [Cache Timing Attack](docs/CACHETIMINGATTACK.md)
      
## Directory Services
  - [X.500](docs/X500.md)
  - [Lightweight Directory Access Protocol (LDAP)](docs/LDAP.md)
  - [Open LDAP](docs/OPENLDAP.md)
  - [Active Directory (AD)](docs/ACTIVEDIRECTORY.md)
    - [Group Policy](docs/ADGPO.md)

## Remote Access
- [Secure Shell (SSH)](docs/SSH.md)
  - [PAM, 2FA, and SSH](docs/PAM2FASSH.md)
- [Remote Desktop](docs/REMOTEDESKTOP.md)
- [Virtual Network Computing (VNC)](docs/VNC.md)
- [Apache Guacamole](docs/GUACAMOLE.md)
  
## Web
  - [HTTP](docs/HTTP.md)
  - [Document Object Model (DOM)](docs/DOM.md)
  - [Secure Socket Layer (SSL)/Transport Layer Security (TLS)](docs/SSLTLS.md)
  - [NGINX Proxy](docs/NGINXPROXY.md)
  - [Browser Extensions](docs/BROWSEREXTENSIONS.md)
  - Attacks
    - [HTTP Strict Transport Security (HSTS)](docs/HSTS.md)
    - [Same Origin/CORS](docs/SAMEORIGINCORS.md)
    - [Server Side Request Forgery (SSRF)](docs/SSRF.md)
    - [Cross Site Request Forgery (CSRF)](docs/CSRF.md)
    - [Cross Site Scripting (XSS)](docs/XSS.md)
    - [Content Security Policy (CSP)](docs/CSP.md)
    - [XML External Entity (XXE)](docs/XXE.md)
    - [HTTP Request Smuggling](docs/REQUESTSMUGGLING.md)
    - [Cross Site Tracing (XST)](docs/XST.md)
    - [Watering Hole Site](docs/WATERINGHOLE.md)

## Application Programming Interfaces (API)
  - [REST](docs/REST.md)
  - [Open API](docs/OPENAPI.md)
  - [Webhook](docs/WEBHOOK.md)
  - Attacks
    - [Broken Object Level Authorization (BOLA)](docs/BOLA.md)
    - Broken Object Property Level Authorization (BOPLA)
    - [Broken Function Level Authorization (BFLA)](docs/BFLA.md)

## Message Queues
- [Message Queue Telemetry Transport (MQTT)](docs/MQTT.md)
- [RabbitMQ](docs/RABBITMQ.md)
- [Apache Kafka](docs/KAFKA.md)
  

## [Databases](docs/DATABASES.md)
  - [Atomicity, Consistency, Isolation, and Durability (ACID)](docs/ACID.md)
  - Data Formats
    - [Avro](docs/AVRO.md)
    - [Parquet](docs/PARQUET.md)
    - [Universal Data Model (UDM)](docs/UDM.md)
  - SQL
    - [JOINs](docs/SQLJOIN.md)
    - [VIEWs](docs/SQLVIEW.md)
  - [Transactions](docs/TRANSACTIONS.md)
  - [Stored Procedures](docs/STOREDPROCEDURES.md)
  - [Relational Databases](docs/RELATIONALDATABASES.md)
    - [Primary Keys](docs/PRIMARYKEY.md)
    - [Foreign Keys](docs/FOREIGNKEY.md)
    - [Normalization](docs/NORMALIZATION.md)
    - MySQL
    - SQL Server
    - Oracle
  - [NoSQL](docs/NOSQL.md)
    - [Apache Cassandra](docs/CASSANDRA.md)
    - Yugabyte
    - [DynamoDB](docs/DYNAMODB.md)
  - Database as a Service
    - BigQuery
    - [Snowflake](docs/SNOWFLAKE.md)
  - Attacks
    - [Diddling](docs/DIDDLING.md)

## Analytics
- Superset
- [MapReduce](docs/MAPREDUCE.md)
- [Apache Spark](docs/APACHESPARK.md)
- [Databricks](docs/DATABRICKS.md)

## [Containers and Orchestration](docs/CONTAINERS.md) 
- [Container Runtime](docs/CONTAINERRUNTIME.md)
- [Docker](docs/DOCKER.md)
- [Kubernetes](docs/K8S.md)
  - [Nodes](docs/K8SNODES.md)
  - [Containers](docs/K8SCONTAINERS.md)
    - [Init Containers](docs/K8SINITCONTAINERS.md)
  - [Pods](docs/K8SPODS.md)
    - [Pod Disruption Budget](docs/K8SPDB.md)
    - [Pod Quality of Service (QoS)](docs/K8SPODQOS.md)
    - [User Namespaces for Pods](docs/K8SUSERNAMESPACES.md)
  - [Deployments](docs/K8SDEPLOY.md)
  - [ReplicaSet](docs/K8SREPLICASET.md)
  - [StatefulSet](docs/K8SSTATEFULSET.md)
  - [DaemonSet](docs/K8SDAEMONSET.md)
  - [Jobs and Cronjobs](docs/K8SJOBS.md)
  - [Networking](docs/K8SNETWORKING.md)
    - [Service](docs/K8SSERVICE.md)
    - [Ingress](docs/K8SINGRESS.md)
      - [HAProxy](https://www.haproxy.org/#desc)
      - [Kong](https://github.com/Kong/kubernetes-ingress-controller#readme)
      - [nginx](https://www.nginx.com/products/nginx-ingress-controller/)
      - [Envoy](https://www.envoyproxy.io)
      - [ngrok](https://github.com/ngrok/kubernetes-ingress-controller)
    - [EndpointSlice](docs/K8SENDPOINTSLICE.md)
    - [Network Policies](docs/K8SNETWORKPOLICIES.md)
    - [DNS](docs/K8SDNS.md)
  - [Hostnames, Labels, and Namespaces](docs/K8SNAMES.md)
  - [Volumes](docs/K8SVOLUMES.md)
  - [ConfigMap](docs/K8SCONFIGMAP.md)
  - [Secrets](docs/K8SSECRETS.md)
  - [Persistent Volumes](docs/K8SPERSISTENTVOLUMES.md)
  - [Volume Snapshots](docs/K8SVOLUMESNAPSHOTS.md)
  - [Securing Kubernetes](docs/SECURINGK8S.md)
  - [SELINUX and Kubernetes](docs/K8SSELINUX.md)
  - Configuration
    - [Kustomize](docs/KUSTOMIZE.md)
    - [Helm](docs/HELM.md)
  - [IAM Roles for Service Accounts (IRSA)](docs/IRSA.md)
  - RBAC

## [CI/CD](docs/CICD.md)
  - [GitHub Actions](docs/GITHUBACTIONS.md)
  - [ArgoCD](docs/ARGOCD.md)
    
## Cloud 
- [Infrastructure as Code](docs/IAC.md)
- [Hyper Converged Infrastructure](docs/HCI.md)
- [AWS](docs/AWS.md)
  - [IAM](docs/IAM.md)
  - [Lambda](docs/LAMBDA.md)
  - [Route53](docs/ROUTE53.md)
  - [Cloud Front](docs/CLOUDFRONT.md)
  - [WAF](docs/WAF.md#aws-web-application-firewall-waf)
  - [Shield](docs/SHIELD.md)
  - [Load Balancer](docs/AWSLOADBALANCER.md)
  - [Auto Scaling Group](docs/AUTOSCALINGGROUP.md)
  - [EC2](docs/EC2.md)
    - [EBS](docs/EBS.md)
  - [S3](docs/S3.md)
  - [GuardDuty](docs/GUARDDUTY.md)
- [Content Delivery Network (CDN)](docs/CDN.md)
- Runtime Security
  - [Web Application Firewall (WAF)](docs/WAF.md)
  - [Rate Limiting](docs/RATELIMITING.md)
  - [Runtime Application Security Protection (RASP)](docs/RASP.md)

## Machine Learning
- [Jupyter Notebooks](docs/JUPYTER.md)
- [TensorFlow](docs/TENSORFLOW.md)
- [pytorch](docs/PYTORCH.md)
- [scikit-learn](docs/SCIKIT.md)

## AI
- Large Language Model (LLM)
- Langchain

## [Monitoring](docs/MONITORING.md)
  - [Time Syncronization](docs/TIMESYNCRONIZATION.md)
  - [Passive](docs/PASSIVEMONITORING.md)
  - [Synthetics](docs/SYNTHETICS.md)
  - [Metrics](docs/METRICS.md)
  - [Events](docs/EVENTS.md)
  - [Logs](docs/LOGS.md)
  - [Traces](docs/TRACES.md)
  - [Alerting](docs/ALERTING.md)
  - [Application Performance Monitoring (APM)](docs/APM.md)
  - [Real User Monitoring (RUM)](docs/RUM.md)



## Security
- [General](docs/GENERALSECURITY.md) 
- [Security Policies](docs/SECURITYPOLICIES.md) 
- [Data Classification](docs/DATACLASSIFICATION.md) 
- [Data Security](docs/DATASECURITY.md) 
- [Physical Security](docs/PHYSICALSECURITY.md)
  - [Fire](docs/FIRE.md)
- [Personnel Security](docs/PERSONNEL.md) 
- [Social Engineering](docs/SOCIALENGINEERING.md) 
- Malware
  - [YARA](docs/YARA.md)
  - [Stealth Virus](docs/STEALTHVIRUS.md)
- Penetration Testing
  - [Vulnerability Scanners](docs/VULNSCANNERS.md)
- [Security Incident and Event Manager (SIEM)](docs/SIEM.md)
  - [Sigma](docs/SIGMA.md)
- [Security Orchestration, Automation, and Response (SOAR)](docs/SOAR.md)

## Endpoint Security
- [Endpoint Detection and Response (EDR)](docs/EDR.md)


  
## [Threat Modeling](docs/THREATMODELING.md)
  - [MITRE ATT&CK](docs/MITREATTACK.md)
  - [STRIDE](docs/STRIDE.md)
  - [PASTA](docs/PASTA.md)
  - [TRIKE](docs/TRIKE.md)
  - [DREAD](docs/DREAD.md)

## Vulnerability Management
  - [Common Weakness Enumerations (CWE)](docs/CWE.md)
  - [Security Content Automation Protocol (SCAP)](docs/SCAP.md)
    - [Open Platform Enumeration (OPE)](docs/OPE.md)
    - [Open Vulnerability and Assessment Language (OVAL)](docs/OVAL.md)
  - [Exploit Protection Scoring System (EPSS)](docs/EPSS.md)
  - [Covert Channels](docs/COVERTCHANNEL.md)
 


## [Laws](docs/LAWS.md) 
- [Office of Foreign Assets Control (OFAC)](docs/OFAC.md)
- [Freedom of Information Act (FOIA)](docs/FOIA.md) 
- [Bank Secrecy Act (BSA)](docs/BSA.md)
- [Privacy Act](docs/PRIVACYACT.md)
- [International Traffic in Arms Regulations (ITAR)](docs/ITAR.md)
- [Fair Credit Reporting Act](docs/FAIRCREDITREPORTINGACT.md)
- [Electronic Communications Privacy Act](docs/ECPA.md)
- [Computer Security Act (CSA)](docs/CSACT.md)
- [Computer Fraud and Abuse Act (CFAA)](docs/CFAA.md)
- [Commmunications Assistance for Law Enforcement Act (CALEA)](docs/CALEA.md)
- [European Union Privacy Law](docs/EUPL.md)
- [Economic Espionage Act](docs/EEA.md)
- [Health Insurance Portability and Accounting Act](docs/HIPAA.md)
- [Digital Millenium Copyright Act (DMCA)](docs/DMCA.md)
- [Children's Online Private Protection Act (COPPA)](docs/COPPA.md)
- [Identity Theft and Assumption Deterence Act](docs/ITADA.md)
- [Gramm-Leach-Bliley Act (GLBA)](docs/GLB.md)
- [EU-US Safe Harbor Framework](docs/EUSAFEHARBOR.md)
- [USA Patriot Act](docs/PATRIOTACT.md)
- [Personal Information Protection and Electronic Documents Act (PIPEDA)](docs/PIPEDA.md)
- [Family Educational Rights and Privacy Act (FERPA)](docs/FERPA.md)
- [Sarbanes Oxley Act (SOX)](docs/SOX.md)
- [Federal Information Security Management Act (FISMA)](docs/FISMA.md)
- [CAN-SPAM](docs/CANSPAM.md)
- [Health Information Technology for Economic and Clinical Health (HIPPA2)](docs/HIPPA2.md)
- [California Online Privacy Protection Act (CalOPPA)](docs/CALOPPA.md)
- [Federal Information Systems Moderization Act (also called FISMA)](docs/FISMA2.md)
- [Export Adminsitration Regulations (EAR)](docs/EAR.md)
- [Cybersecurity Information Sharing Act (CISA)](docs/CISA.md)
- [Privacy Shield](docs/PRIVACYSHIELD.md)
- [General Data Protection Regulation (GDPR)](docs/GDPR.md)
- [California Consumer Protection Act (CCPA)](docs/CCPA.md)
- [Personal Information Protection Law (PIPL)](docs/PIPL.md)
- [California Privacy Rights Act (CPRA)](docs/CPRA.md)


## Standards
- [Center for Information Security (CIS)](docs/CIS.md) 
- [Cybersecurity Maturity Model Certification (CMMC)](docs/CMMC.md) 
- [Control Objectives for Information Technology (COBIT)](docs/COBIT.md) 
- [Cloud Security Alliance (CSA)](docs/CSA.md) 
- [FIPS 140-2](docs/FIPS.md)
- Google
  - [Supply Chain Levels for Software Artifacts (SLSA)](docs/SLSA.md)
- [International Standards Organziation (ISO)](docs/ISO.md)
  - [ISO 7498: OSI Model](docs/ISO7498.md)
  - [ISO 15408: Common Criteria for Information Technology Security Evaluation (CC)](docs/ISO15408.md)
  - [ISO 27071: Cloud Controls](docs/ISO27071.md)
  - [ISO 28031: Information technology — Security techniques — Guidelines for information and communication technology readiness for business continuity](docs/ISO27031.md)
- [Information Technology Service Management (ITSM)/ Information Technology Infrastructure Library (ITIL)](docs/ITSM.md)
- [North American Electric Reliability Corporation - Critical Infrastructure Protection (NERC CIP)](docs/NERC.md) 
- [NIST](docs/NIST.md)
  - [NIST 800-14: Generally Accepted Principles and Practices for Securing Information Technology Systems](docs/NIST80014.md)
  - [NIST 800-18: Guide for Developing Security Plans for Federal Information Systems](docs/NIST80018.md)
  - [NIST 800-34: Contingency Planning Guide](docs/NIST80034.md)
  - [NIST 800-84: Guide to Test, Training, and Exercise Programs for IT Plans and Capabilities](docs/NIST80084.md)
  - [NIST 800-137: Information Security Continuous Monitoring (ISCM) for Federal Information Systems and Organizations](docs/NIST800137.md)
  - [NIST Secure Software Development Framework (SSDF)](docs/NISTSSDF.md)
- [PCI-DSS](docs/PCIDSS.md) 
- [SOC2](docs/SOC2.md) 
- [Supply Chain](docs/SUPPLYCHAIN.md) 
- [X.509](docs/X509.md) 

## Process Management
- [Getting Started as a CISO](docs/CISOSTART.md) 
- [Planning](docs/PLANNING.md)
- Project Management
  - [Work Breakdown Structure (WBS)](docs/WBS.md)
- [Change Management](docs/CHANGEMANAGEMENT.md)
- [Capability Maturity Model (CMM)](docs/CMM.md)
- [Agile](docs/AGILE.md)
  - [Spike Documents](docs/SPIKE.md)
- [Code Reviews](docs/CODEREVIEW.md) 
- [DevOps](docs/DEVOPS.md) 
- [Site Reliability Engineering (SRE)](docs/SRE.md)
- [SLO, SLA, and Error Budget](docs/SLOSLA.md)
- [Incident Response](docs/INCIDENTRESPONSE.md) 
- [Risk Management](docs/RISKMGMT.md) 
- [Security Engineering](docs/SECURITYENGINEERING.md) 
- [Business Continuity Planning (BCP)/Disaster Recovery (DR)](docs/BCPDR.md) 
- [Investigations](docs/INVESTIGATIONS.md)
  - [Best Evidence Rule](docs/BESTEVIDENCE.md)
  - [Parol Rule](docs/PAROL.md)
  - [Hearsay Rule](docs/HEARSAY.md)
  

## People Management
- [Ethics](docs/ETHICS.md)
- [Culture](docs/CULTURE.md) 
- [Recruiting](docs/RECRUITING.md)
- [Onboarding](docs/ONBOARDING.md)
- [Accountability](docs/ACCOUNTABILITY.md)
- [Team Cohesion](docs/COHESION.md)
  - [Stages of team behaviour: Forming, Storming, Norming,and Performing](docs/FORMINGNORMING.md)
- [Team Topologies](docs/TEAMTOPOLOGIES.md)


  
## Business
- [Basic Finance](docs/BASICFINANCE.md) 
- [Federal Reserve](docs/FED.md)
- Private Markets
  - [Indicator of Interest (IOI)](docs/IOI.md)


