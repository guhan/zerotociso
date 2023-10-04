# Active Directory Group Policy 
An Active Directory Group Policy (GPO) is a collection of settings and policies that can be applied to users and computers within an Active Directory domain. Group Policies are used to manage various aspects of the Windows operating system and network behavior. While the actual appearance of a Group Policy is not something you see directly, it is defined and configured using the Group Policy Management Console (GPMC) on a Windows server. 

## Group Policy Object (GPO)
A Group Policy Object is a container that holds the configuration settings and policies. It is created and managed within the Group Policy Management Console (GPMC). Each GPO can be linked to one or more Active Directory containers, such as a domain, organizational unit (OU), or site.
## Settings and Policies
A GPO contains a wide range of settings and policies that can be configured to control various aspects of Windows behavior and security. These settings can include

- Security Settings
Enforce password policies, account lockout policies, and security options.
- Software Installation
Deploy and manage software applications to users and computers.
- Folder Redirection
Redirect user profile folders like Documents, Desktop, and Favorites to network locations.
- Desktop Settings
Configure desktop appearance, shortcuts, and screensavers.
- Local Policies
Set local security policies on computers.
- Network Configuration
Define network settings, such as drive mappings, scripts, and proxy settings.
- Security Options
Specify user rights assignments and audit policies.
- Windows Firewall Settings
Configure firewall rules and exceptions.
- Group Policy Preferences
Define additional settings, such as drive mappings and printer configurations.
- Group Policy Administrative Templates
Modify Windows Registry settings for specific components and applications.
## Scope of Application
GPOs can be linked to specific Active Directory containers, which determine where the GPO settings are applied. For example, a GPO linked to an OU containing user accounts will apply its settings to those users.
## Inheritance
Group Policies follow an inheritance model, where settings defined in higher-level containers (e.g., domain level) apply to all objects within lower-level containers (e.g., OUs). However, settings at lower levels can override or supplement those at higher levels.
## Security Filtering
Administrators can further control which users and computers a GPO applies to by using security filtering. This involves specifying user or group permissions on the GPO, ensuring that only authorized users and computers receive the GPO settings.
## WMI Filtering
Windows Management Instrumentation (WMI) filters allow administrators to apply GPOs based on specific conditions, such as the operating system version or hardware attributes of a target computer.
## Enforcement and Block Inheritance
Administrators can enforce a GPO to ensure that it takes precedence over conflicting settings from higher-level containers. They can also block inheritance at lower levels to prevent settings from higher levels from affecting objects within a specific container.
## Resultant Set of Policy (RSoP)
The RSoP tool allows administrators to simulate the effects of GPOs on specific users and computers, helping them understand how GPOs are applied and which settings take precedence.
