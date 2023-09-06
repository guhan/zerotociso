# Operating Systems

### Processing Types
- **Single State**: only one security level at a time
- **Multi State**: multiple states at one time

### Processing modes
- **privileged, kernel, system, supervisor**:
  - full privileges
- **problem state, user**:
  - limited privileges
  - CPU only allows a subset of full instruction set

### Protection Rings
Organize code and components in an operating system. 

![Protection Rings](/images/protectionrings.png)

### Process States
The lifecycle of a process is illustrated below. 
- Supervisory state: when a process needs to perform a actoin that requires priviliges
![Process States](/images/Process-State-1.png)

### Security Modes
US Government has approved security modes for systems with classified information. 
- Dedicated:
  - Each user must have security clearance for all info
  - Each user must have access approval all info
  - Each user must have a valid need
- System High Mode:
  - Each user must have a valid security clearance
  - Each user must have access approval _for all info_ 
  - Must have need to know but _not for all information_
- Compartmented:
  - Each user must have security clearance for all info
  - Each user must have access approval _for just what they need_
  - Must have a need to know for all information they have access to
- **Compartmented mode workstations (CMWs)**: users with necessary clearances can process multiple compartments of data at the same time
  - Sensitivity label: what level an object must be protected
  - Information label: prevent data overclassification and add metadata
- Multilevel:
  - Some users do not have valid security for all info
  - each user must have access approval for all information they will access on the system
  - each user must ahve a valid need to know 
