# Mandatory Access Control (MAC)
Mandatory Access Control (MAC) is a security model and access control mechanism used in computer systems and networks to enforce **strict, hierarchical access controls based on security labels and predefined rules**. Unlike discretionary access control (DAC), where users have some discretion in determining access permissions, MAC enforces access decisions independently of user discretion.

- [Lattice](LATTICEACCESSCONTROL.md) based model
- Heirarchal
- Compartmented

## Security Labels
**Each resource** (such as files, processes, or data objects) **and each user** or system entity is assigned a security label or classification. These labels typically consist of levels (e.g., "Top Secret," "Secret," "Confidential," "Unclassified") and categories (e.g., "Finance," "Human Resources," "Research").

## Security Policy
The system operates based on a predetermined security policy that defines the rules for access control. The security policy typically includes rules that specify which subjects (users or processes) can access specific objects (resources) based on their security labels.

## No Discretion
In a MAC system, users and administrators do not have discretion to change or modify access permissions. Access decisions are solely based on the security labels and the rules defined in the security policy.

## Hierarchical Enforcement
MAC enforces access controls hierarchically, meaning that a subject with a particular security label can access objects with equal or lower security labels. However, access to objects with higher security labels is typically restricted. 
- No write down

## Need-to-Know Principle
MAC systems often follow the "need-to-know" principle, which means that users or processes are only granted access to information or resources if they have a legitimate need to access them based on their job roles or duties.

## Government and Military Use
MAC is commonly used in government, military, and high-security environments where strict control over information and data is essential to prevent unauthorized access and data leaks.

## Complexity and Administration
Implementing and managing MAC systems can be complex, as it requires careful classification of resources, users, and processes, and the definition of precise access control rules. This complexity can make MAC less suitable for general-purpose computing environments.

## Examples
The U.S. Department of Defense's (DoD) Multilevel Security (MLS) policy, as defined by the Trusted Computer System Evaluation Criteria (TCSEC), is an example of a MAC system. Additionally, the Bell-LaPadula security model and the Biba integrity model are well-known MAC models.
