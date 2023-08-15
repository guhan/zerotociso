# Evalutating Security Controls
The following frameworks are used to evaluate security controls

## Trusted Computer System Evaluation Criteria (TSSEC) aka Rainbow Series
1980s at the DoD

4 major categoroies
- A: Verfified protection. Highest level
  - development cycle is also considered
- B: Mandatory protection
  - more granularity
  - B1: labeled security
  - B2: Structued position, no covert channels
  - B3: Security domains ie more separation and isolation of unrleated process
- C: Direcretionary protection 
  - basic access control
  - C1: discretionary security protection
  - C2 Controlled access protection (media clensing)
- D: Minimal protection. Evaluated but do not meet requirements to belong in another category

### Books
- Orange: standalone systems
- Red: Network
- Green: Passwords

### Why abandoned?
- Not much once access is granted
- Tech evolved fast
- Doesn't address personnel, physical, or procedural policy

## Information Technology Security Evaluation Criteria (ITSEC)
made in EU

- systems are Targets of Evaluation (TOE)
- addresses integrity also
- has no TCB

## Common Criteria
A global effort to merge TSSEC, ITSEC and bring it all up to date. 
More details in ISO 15408 Evaluation Criteria for Information Technology Security

Has three parts
- Intro and General Model
- Security Functional Requirements
- Assurance

### Objectives
- add buyer confidence
- eliminate duplicate evaluationss
- make certification more cost effective
- adhere to high standards
- promote evaluation

### Key Concepts
- **protection profile**: the security desires of the customer
- **security targets**: claims made by the vendor
- **Evaluation Assurance Level (EAL)**: published or marketed levels


EALs: 0 (minimal) to 7(verified security design)
