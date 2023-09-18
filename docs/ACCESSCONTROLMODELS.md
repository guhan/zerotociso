# Access Control Models

## Key Concepts
- **Subject**: user or process that makes a request to the resource
- **Object**: the resource that the user or process wants to access
- **Closed System**: works well with a narrow range of other systems, often proprietary
- **Open System**: designed on agreed up open industry standards
- **Security Model**: a way for designers to map abstract statements into a security policy that prescribes
  the algorithms and data structures.
- **Security Token**: a seprate object that is associated with a resource and describes its security
  attributes.
- **Capabilities List**: maints a row of security attributes for each controlled object.
- **Security Label**: permanent part of the object to which it is attached


## Techniques to ensure [CIA](GENERALSECURITY.md)
- **Confinement**: process can read from and write only from certain memory locations and resources,
  also known as _sandboxing_
- **Bounds**: limits set on memroy and resources it can access. The bounds state the area in which
  a process is confined.
- **Isolation**: when a process is confined in bounds it is running in isolation
- **Controls**: uses access rules to limit the access of a subject to an object
  - Mandatory Access Controls (MAC): hard constraints on what the subject can access
  - Discretionary Access Controls(DAC): subject can define the controls
- **Trusted System**: all protection mechanisms work together to process sensitive data for many types of
  users while maintaining a stable and secure computing environment
- **Assurance**: the degree of confidence in satisfaction of security needs





## Access Control Models
- **Discretionary Access Controls**:
  - Owner provides access or deny to objects
- **Role Based Access Controls**:
  - permissions are granted based on user or group membership
- **Rule Based Access Controls**:
  - global rules that apply to all subjects
  - example is a firewall
- **Attribute Based Access Controls**:
  - global rules that consider additional attributes like location 
- **Mandatory Access Controls**:
  - identity based
  - define labels for each domain
  - very prohibitive 

