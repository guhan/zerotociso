# Security Design and Models

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



## Security Models
### Trusted Computing Base
A combination of hardware,software,and controls that work together to form a trusted base to enforce your 
security policy
- Should be as small as possible to easily evaluate
- Not every component needs to be trusted
- **Security Parameter**: Imaginary boundary that separates the TCB from the rest of the system
- **Trusted Path**: A channel established with strict standards to allow necessary communication without
  exposing security vulnerabilities
- **Reference Monitor**: part of the TCB that validates access to every resource before granting access access
  - Security kernel: the parts of the TCB that implement the reference monitor functions

### State Machine Model
System is always secure no matter what state it is in
- Always boots into a secure state

#### Formal State Machine (aka State Machine or finite-state machine) 
is a mathematical model used to describe the behavior of systems that can exist in a finite number of 
distinct states and transition between those states based on certain inputs or events. State machines are 
commonly used in computer science, engineering, and various other fields to model and analyze 
systems with discrete and sequential behavior.

A formal state machine consists of the following components:

- States: These are distinct conditions or situations that a system can be in. Each state represents a specific configuration or mode of operation for the system.
- Transitions: Transitions define the way the system changes from one state to another in response to inputs, events, or conditions. Transitions are triggered by certain events or conditions, and they dictate how the system's state changes.
- Inputs/Events: These are external factors that influence the state transitions. Events trigger the state transitions, and the behavior of the system depends on which event occurs.
- Outputs/Actions: Outputs or actions are the consequences or responses of the system to the state transitions. These can include changes in the system's behavior, updates to data, or interactions with the environment.

### Information Flow Model
Focuses on the flow of information
- Designed to prevent unauthorized, insecure, or restricted information flow, often between _different levels
  of security_
- Dictates how an object can transition between two states
- Types of flows:
  - Cascading: input from one system comes from another system
  - Feedback: one system inputs into another and it in turns inputs the first system
  - Hookup: systems sends input to one system and also external entitites

### Noninterference Model
How do actions of a subject at a higher or lower security level affect the system state

### Take Grant Model
Employs a directed graph to dictate how hights can be passed from one subject to or from another subject

### Access Control Matrix
Table of subjects and objects and indicates the functions that each subject can perform on each object
- Each column is an ACL
- Each row is a capabilities list
- Implementation:
  - create a list of object and subjects
  - create a function that maps the objects to the subjects
 
### Bell-LaPadula Modula
- **Multilevel classification policy**: subjects can access resources at or below their clearance level.
- Blocks lower clearance from accessing higher clearance
- Simple Security Property: subject may not read informatino at a higher sensitivity level (no read up)
- Star Secuirty Property: subject may not write information to a lower sensitivy level (no write down)
- Discretion Security Property: uses an access matrix to enforce access control

#### Lattice-based access control
Resources are classified and users are assigned different levels of security clearance or authorization. The lattice structure helps to model the hierarchy of security levels and the relationships between different levels. The access control decisions are then made based on this lattice structure.

Here's how it generally works:

- Lattice Structure: The lattice structure is established with a set of security levels organized in a hierarchical manner. Each level represents a certain level of access privilege, and relationships between levels are defined, such as "greater than" or "less than" relationships.
- Resource Classification: Resources (files, data, applications, etc.) are classified according to the security levels required to access them.
- User Clearance: Each user or user group is assigned a security clearance level. This level indicates the highest level of access they are allowed to have.
- Access Decision: When a user attempts to access a resource, the lattice-based access control system checks the user's clearance level against the security classification of the resource and the lattice structure. Access is granted if the user's clearance is at least as high as the required level for the resource, following the lattice relationships.


### Biba Model
Addresses integrity more than confidentiality
- Better for commercial vs military
- Prevent modificiton of objects by unauthorized subjects
- Prevent unauthorized modification of objects by authorized subjects
- Protect internal and external object consistency
- Does not address access control no way to assign or change a subjects classification level

**Difference from Bell-LaPadula**
- Simple Security Property: subject may not read informatino at a lower sensitivity level (no read down)
- Star Secuirty Property: subject may not write information to a higher sensitivity level (no write up)


### Clark-Wilson Model
Defines each data item and allows modifications through a small set of programs
- objects are accessed through programs
- **Constrained Data Item (CDI)**: any item where integrity is protected by security model
- **Unconstrained Data Item (UDI)**: item where integrity is not controlled by the security model
- **Integrity Verification Procedure(IVP)** - scans items and confirms their integrity
- **Transformation Procedures (TPs)**: the _only_ procedures allowed to modify a CDI
- **Restricted Interface Model**: uses classification based restrictions to fofer only subject specific
  authorized information and functions.

### Brewer and Nash Model (aka Chinese Wall)
Permits access controls to change dynamically based on users previous activity
- Prevents conflicts of interest, person in company A working woth both Company B and C where B and C
  are competitors of each other.

### Goguen-Meseguer Model
integrity model 
- foundatino of the noninterference conceptual theories
- predetermin the set or domain (list of objects) that a subject can access

### Sutherland Model
integrity model 
- defining a set of system states, initial states, integrity is maintained and interference is prevented

### Graham-Denning Model
secure creation and deletion of both subjects and objects
