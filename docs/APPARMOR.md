# App Armor
AppArmor, short for Application Armor, is a Linux security module (LSM) that provides Mandatory Access Control (MAC) for processes and applications. It is designed to restrict the capabilities and access rights of individual programs to enhance the security of a Linux system. AppArmor primarily focuses on defining and enforcing security policies based on the concept of profiles.

## Security Profiles
AppArmor uses security profiles to specify the permissions and restrictions for individual processes or applications. These profiles define what resources a program can access and what actions it can perform.
## Path-Based Security
AppArmor profiles are often path-based, which means they define access control based on the paths to files and directories that a program needs to access. This makes it easier to create and maintain profiles.
## Whitelisting Approach
AppArmor follows a whitelisting approach to security, which means that it explicitly defines what is allowed, and everything else is denied by default. This is in contrast to blacklisting, where specific disallowed actions must be listed.
## Flexible Policy Language
AppArmor uses a policy language that allows system administrators to specify security policies in a readable and human-understandable format. Profiles can be written in plain text files with specific syntax.
## Integration with Systemd and Containers
AppArmor integrates well with systemd, the init system used in many Linux distributions. It can also be used with container technologies like Docker to add an additional layer of security to containerized applications.
## Run-Time Enforcement
AppArmor enforces security policies during the runtime of applications. If a program attempts to perform an action that is not allowed by its profile, AppArmor will block the action and generate audit logs.
## Audit and Logging
AppArmor provides auditing and logging capabilities, allowing administrators to monitor and review security-related events and policy violations.
## Ease of Use
AppArmor is known for its ease of use and is often considered more approachable for beginners compared to other Mandatory Access Control systems like SELinux.
