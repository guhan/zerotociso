# # Trusted Computing Base
A combination of hardware,software,and controls that work together to form a trusted base to enforce your 
security policy


- Should be as small as possible to easily evaluate
- Not every component needs to be trusted
- **Security Parameter**: Imaginary boundary that separates the TCB from the rest of the system
- **Trusted Path**: A channel established with strict standards to allow necessary communication without
  exposing security vulnerabilities
- **Reference Monitor**: part of the TCB that validates access to every resource before granting access access
  - Security kernel: the parts of the TCB that implement the reference monitor functions
