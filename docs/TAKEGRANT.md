# Take Grant Model

The Take-Grant model is a formal security model used in computer science and information security to analyze and reason about access control and permissions within a system. It is primarily used to evaluate the security of systems that involve subjects (entities capable of taking actions) and objects (entities on which actions can be taken), such as computer systems, networks, and software applications. The Take-Grant model is a simple and intuitive representation of access control relationships.

In the Take-Grant model, the primary entities are:

- **Subjects**: Subjects represent entities that can take actions or operations. These are often users, processes, or programs that interact with the system.
- **Objects**: Objects represent entities on which actions can be taken. These are often files, resources, or data within the system.

The model is based on the concept of "takes" and "grants," which represent the transfer of permissions from one entity to another. 

Employs a directed graph to dictate how hights can be passed from one subject to or from another subject

## Rules
- **Take**: Allows a subject to take rights over an object
- **Grant**: Allows a subject to grant rights to an object
- **Create**: Allows a subject to create new rights to itself 
- **Remove**: Allows a subject to remove rights it has

## Initial State
The model starts with an initial state where subjects have certain permissions or capabilities. These permissions are represented as tokens.

## Takes and Grants
- Subjects can take tokens from objects, and they can also grant tokens to other subjects.
- Taking a token represents acquiring a permission
- Granting a token represents delegating that permission.
  
## Transition Rules
The model defines transition rules that dictate under what conditions a subject can take a token from an object or grant a token to another subject. These rules are based on the system's access control policies and security mechanisms.
## State Changes
As subjects take tokens from objects and grant tokens to other subjects, the system's state changes. These state changes represent the evolution of permissions and access rights within the system.
## Security Analysis
The Take-Grant model is used to analyze the system's state and determine whether it satisfies security requirements. Security properties can be defined, such as "no subject should be able to take a token it is not initially granted," and the model is checked against these properties to identify security vulnerabilities.

