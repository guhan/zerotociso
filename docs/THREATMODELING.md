# Threat Modeling

## What is the MITRE attack framework?

The MITRE ATT&CK framework (Adversarial Tactics, Techniques, and Common Knowledge) is a comprehensive knowledge base and model that categorizes and describes various adversary tactics, techniques, and procedures (TTPs) used in cyberattacks
- Tactic: A high-level category that represents the adversary's overall objective or goal. Examples of tactics include initial access, execution, persistence, privilege escalation, defense evasion, and exfiltration.


- Technique: Specific methods or techniques used by adversaries to achieve their objectives within each tactic. Techniques describe the steps and actions an attacker may employ during an attack. For example, a technique within the initial access tactic could be spear-phishing or exploiting a software vulnerability.


  - Sub-technique: A more granular variation or refinement of a technique. Sub-techniques represent specific implementation details or variations of techniques. They provide more detailed insight into the specific methods used by adversaries.


- Mitigation: Recommended defensive measures, best practices, or countermeasures that organizations can implement to prevent or detect specific techniques or tactics. Mitigations help organizations develop effective security controls and strategies to protect against known attack techniques.

## What is STRIDE?
STRIDE is a threat modeling framework used to identify and categorize potential threats in software systems and applications.

- Spoofing: This threat category focuses on the ability of an attacker to impersonate or masquerade as a legitimate user, system, or entity. It includes threats such as identity spoofing, IP address spoofing, or application spoofing.


- Tampering: Tampering refers to the unauthorized modification or alteration of data, configurations, or code within a system. This category includes threats like unauthorized data modification, code injection, or tampering with cryptographic mechanisms.


- Repudiation: Repudiation threats involve an attacker's ability to deny or dispute their actions or transactions within a system. It includes threats such as transaction repudiation, log manipulation, or falsifying evidence.

- Information Disclosure: Information disclosure threats focus on the unauthorized exposure or leakage of sensitive data. This category includes threats like data leaks, unauthorized access to sensitive information, or insecure transmission of data.

- Denial of Service (DoS): Denial of Service threats involve attempts to disrupt or degrade the availability or performance of a system or service. This can be achieved through actions such as flooding the system with excessive requests, resource exhaustion, or application crashes.


- Elevation of Privilege: Elevation of Privilege threats involve an attacker gaining higher levels of access or permissions than intended within a system. It includes threats such as privilege escalation, bypassing access controls, or gaining administrative privileges.

## What is the PASTA Framework?
The seven stages of PASTA threat modeling:
1. Define the Objectives
2. Define the Technical Scope
3. Decompose the Application
4. Analyze the Threats
5. Vulnerability Analysis
6. Attack Analysis
7. Risk and Impact Analysis
