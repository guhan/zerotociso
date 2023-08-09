# Data Security

## Types of sensitive data
- **Personally Identifiable Information (PII)**: any information that can identify an individual
  - Name
  - Address
  - Social Security Number
  - Date of Birth
  - Email Address
  - Phone Number
  - Passport Number
  - Driver's License Number
  - Financial Information (e.g., credit card numbers, bank account numbers)
  - Biometric Data (e.g., fingerprints, facial recognition data)
  - Medical Information
  - IP Address (in some contexts)
  - Online Identifiers (e.g., usernames, account numbers)
- **Personal Health Information (PHI)**: any health related information that can be related to a specific individual
  - Patient's Name
  - Address
  - Date of Birth
  - Social Security Number
  - Medical Record Number
  - Health Insurance ID Number
  - Diagnosis and Treatment Information
  - Laboratory Results
  - Prescription Information
  - Radiology Images and Reports
  - Other Identifying Information
- **Proprietary Data**: Any data that helps and organziation get a competitive edge

## Data States
- Data at rest: stored on media like hard drives, USB, Storage Area Networks, and backup tapes
- Data in Transit: data sent over a network using wired or wireless communication
- Data in Use: dta in memory or temporary storage buffers (cache) as application is processing it

## Handling Data
- Marking data: adding a label that clearly identifies the classification level
  - Header/Footer on documents
  - Physical Label
- Storing data: encrypt or lock it
- Destroying Data:
  - Avoid _Data Remanence_ ie data left on media after it was supposedly erased, with a degausser which generates a large magnetic field
  - For SSD's use destruction
  - Erasing Data: Only removes the link to the data on the disk
  - Clearing Data: overwriting the data, ie with zeros
  - Purging Data: repeat the clearing process multiple times
  - Degaussing: use a strong magnetic field, wont work on CDs,DVDs, or SSDs
  - Destruction: vaporize it
- Asset Retention: Ensure that data is retained for as long as it is needed

## Data Protection
- Symmetric encryption: Same key is used to encrypt and decrypt data
  - Advanced Encryption Standard (AES): supports keys of 128, 192 and 256 bits
  - Triple DES (3DES): uses 112 or 168 bit keys. Used by credit cards and made more secure with a PIN
  - Blowfish: keysize from 32 to 448 bits. bcrypt uses Blowfish, and is used to encrypt Linux passwords
- Pseudonymization: using pseudonyms (artificial identifiers) to represent the data
- Anonymization: remove relevant data that could identify the person

## Data Ownership
Refer to NIST SP 800-18
- Data owner: person who is ultimately responsible for the data
- Asset owner: System owner who owns a system or process
- Business owner: or mission owner is a program manager
- Data processor: natural or legal person which processes data on behalf of the data controller


 
