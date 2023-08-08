# Sigma

Sigma is an open-source project and a generic signature format for describing detection rules in a consistent and platform-independent way. 
It is used for creating and sharing detection rules for various security information and event management (SIEM) systems, intrusion detection 
systems (IDS), and other security tools.

The primary goal of Sigma is to provide a common language for expressing detection logic across different security platforms. This _makes 
it easier for security analysts and researchers to create and share detection rules that can be used across a 
variety of security tools_ without having to write platform-specific rules for each system.

### Key features of Sigma include:

- Cross-Platform Compatibility: Sigma rules can be translated or converted into the native formats of different SIEMs and security tools,
  allowing the same detection logic to be used across multiple platforms.
- Simple and Readable Syntax: Sigma rules use a simple and human-readable YAML syntax that is easy to write and understand.
  This helps security analysts quickly create and share detection logic.
- Wide Range of Detection Scenarios: Sigma supports a wide range of detection scenarios, including network traffic analysis,
  host-based detection, application-level detection, and more.
- Community and Sharing: Sigma has an active user community that shares and contributes to a repository of pre-built detection
  rules, making it easier to adopt and use effective detection logic.
- Support for Multiple Data Sources: Sigma rules can be written to match patterns and conditions in various data sources, such
  as log files, network traffic, and more.
- Extensibility: Sigma rules can be extended with custom attributes and mappings to support specific SIEMs or tools.
- Integration with SIEMs and Security Tools: SIEMs and security tools that support Sigma can ingest and apply Sigma detection rules
  to enhance threat detection capabilities.

### Example
Here's a simplified example of a Sigma rule written in YAML format that detects failed login attempts in Windows Event Logs. This rule could 
be used to identify potential brute-force attacks on Windows systems.

```
title: Failed Logins Detection
id: windows_failed_logins
description: Detects failed login attempts in Windows Event Logs
status: experimental
logsource:
    product: windows
    service: security
detection:
    selection:
        EventID: 4625  # Event ID for failed logon
    condition: 'Event[''Status'' == "0xc000006d" or Event[''Status'' == "0xc000006e"]'
fields:
    - EventID
    - TargetUserName
    - WorkstationName
    - SourceAddress
    - Status
falsepositives:
    - Legitimate failed logon attempts
level: low
```

In this Sigma rule:

- title provides a name for the rule.
- id is a unique identifier for the rule.
- description offers a brief description of what the rule detects.
- status indicates the rule's development status (e.g., "experimental").
- logsource defines the source of logs for the rule (Windows Security Event Logs).
- detection specifies the conditions to detect failed login attempts:
- selection filters events with EventID 4625 (failed logon).
- condition uses a logical OR to match specific Status values associated with failed logon attempts.
- fields lists the relevant fields to include in the detection output.
- falsepositives provides examples of legitimate failed logon attempts that might trigger the rule.
- level indicates the severity level of the rule.

This Sigma rule helps identify failed login attempts in Windows Event Logs, focusing on specific Event IDs and Status values. 
