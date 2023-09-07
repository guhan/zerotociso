# Threat Modeling

## Basic Steps
### Identify Threats
- Focus on Assets
- Focus on Attackers
- Focus on Software

### Determine and Diagram Potential Attacks
- Create flow diagrams to see how users interact with your application
- Identify attacks on each element of the diagram

### Perform Reduction Analysis
Decompose the application to understand the logic behind how each piece interacts with each other. 

Identify these 5 key concepts: 
- Trust boundaries: where does trust or security change
- Data flow paths: how does data move in the application
- Input points: Where does external input get processed
- Privileged Operations: Where are greater privileges required
- Details about Security Stance and approach: look at the security policies and design documents

### Prioritization and Response
Rank or rate the threats. A common way is:  
```
probability * damage potential Ranking (High/Med/Low)
```

## What is the MITRE attack framework?

The MITRE ATT&CK framework (Adversarial Tactics, Techniques, and Common Knowledge) is a comprehensive knowledge base and model that categorizes and describes various adversary tactics, techniques, and procedures (TTPs) used in cyberattacks
- **Tactic**: A high-level category that represents the adversary's overall objective or goal. Examples of tactics include initial access, execution, persistence, privilege escalation, defense evasion, and exfiltration.


- **Technique**: Specific methods or techniques used by adversaries to achieve their objectives within each tactic. Techniques describe the steps and actions an attacker may employ during an attack. For example, a technique within the initial access tactic could be spear-phishing or exploiting a software vulnerability.


  - **Sub-technique**: A more granular variation or refinement of a technique. Sub-techniques represent specific implementation details or variations of techniques. They provide more detailed insight into the specific methods used by adversaries.


- **Mitigation**: Recommended defensive measures, best practices, or countermeasures that organizations can implement to prevent or detect specific techniques or tactics. Mitigations help organizations develop effective security controls and strategies to protect against known attack techniques.

## What is STRIDE?
STRIDE is a threat modeling framework used to identify and categorize potential threats in software systems and applications.

- **Spoofing**: This threat category focuses on the ability of an attacker to impersonate or masquerade as a legitimate user, system, or entity. It includes threats such as identity spoofing, IP address spoofing, or application spoofing.


- **Tampering**: Tampering refers to the unauthorized modification or alteration of data, configurations, or code within a system. This category includes threats like unauthorized data modification, code injection, or tampering with cryptographic mechanisms.


- **Repudiation**: Repudiation threats involve an attacker's ability to deny or dispute their actions or transactions within a system. It includes threats such as transaction repudiation, log manipulation, or falsifying evidence.

- **Information Disclosure**: Information disclosure threats focus on the unauthorized exposure or leakage of sensitive data. This category includes threats like data leaks, unauthorized access to sensitive information, or insecure transmission of data.

- **Denial of Service (DoS)**: Denial of Service threats involve attempts to disrupt or degrade the availability or performance of a system or service. This can be achieved through actions such as flooding the system with excessive requests, resource exhaustion, or application crashes.


- **Elevation of Privilege**: Elevation of Privilege threats involve an attacker gaining higher levels of access or permissions than intended within a system. It includes threats such as privilege escalation, bypassing access controls, or gaining administrative privileges.

## What is the PASTA Framework?
The seven stages of PASTA threat modeling:
1. Define the Objectives
2. Define the Technical Scope
3. Decompose the Application
4. Analyze the Threats
5. Vulnerability Analysis
6. Attack Analysis
7. Risk and Impact Analysis

## What is the TRIKE Framework?
TRIKE provides a structured approach to cybersecurity risk assessment and management, helping organizations proactively address potential security threats and vulnerabilities.

### Key Components of TRIKE Methodology:

- Threat Assessment: The first step involves identifying potential threats that could exploit vulnerabilities in an organization's systems or networks. Threat sources, motivations, and capabilities are analyzed to understand the likelihood of specific threats.
- Risk Assessment: TRIKE considers the potential impact of identified threats on the organization's assets and operations. It assesses the likelihood and consequences of successful attacks to prioritize risks and determine where to focus mitigation efforts.
- Vulnerability Assessment: The methodology evaluates the organization's vulnerabilities and weaknesses that could be exploited by potential threats. This includes analyzing the security measures in place, such as software flaws, configuration errors, or misconfigurations.
- Countermeasure Selection: After identifying threats, risks, and vulnerabilities, the next step is to select appropriate countermeasures and security controls to mitigate the identified risks effectively.
- Mitigation Planning: TRIKE helps organizations develop a comprehensive mitigation plan that outlines the steps needed to address the identified risks. The plan includes the implementation of security controls, monitoring, incident response, and other measures to enhance cybersecurity resilience.
- Continuous Improvement: TRIKE emphasizes the need for ongoing assessment and adaptation of security measures to address evolving threats and risks. Regular reviews and updates to the risk assessment and mitigation strategies are crucial for maintaining a strong security posture.

## What is the DREAD Framework?
DREAD is a risk assessment model used in cybersecurity and software development to evaluate and prioritize potential risks associated with a system, application, or software component. The model helps teams identify and understand the severity of specific risks, allowing them to focus their efforts on addressing the most critical issues.

### "DREAD" is an acronym, with each letter representing a different attribute used to assess risks:

- Damage Potential: This attribute evaluates the potential impact or damage that could result from the exploitation of a vulnerability. It assesses the extent of harm to the organization, data, systems, or users.
- Reproducibility: Reproducibility refers to how easily an attacker can reproduce or exploit a vulnerability. Vulnerabilities that are easily replicable may pose higher risks.
- Exploitability: Exploitability assesses the level of difficulty or skill required for an attacker to exploit the vulnerability successfully. Vulnerabilities with high exploitability are more likely to be targeted.
- Affected Users: This attribute considers the number of users or systems that could be affected by the vulnerability. Risks that impact a large number of users are generally considered more severe.
- Discoverability: Discoverability refers to how easy it is for an attacker to identify the vulnerability. Vulnerabilities that are easy to find may be more likely to be exploited.

