# SLSA
SLSA (Supply Chain Levels for Software Artifacts) is a framework and set of best practices developed by Google to enhance the security and integrity of software supply chains.

- SLSA Level 1 (Basic):
At Level 1, basic security practices are implemented, such as storing artifacts in a tamper-evident manner and providing encryption for transport. This level focuses on foundational security measures.
- SLSA Level 2 (Verified):
Level 2 adds verification of the software artifacts through reproducible builds. It ensures that software can be consistently built from source code, and the resulting binaries can be verified to match the expected outputs. This reduces the risk of supply chain attacks and tampering.
- SLSA Level 3 (Reproducible):
At Level 3, full end-to-end reproducibility is achieved, including the entire software build process and its dependencies. This level ensures that any user can verify and reproduce the build with the same results as the original provider.
- SLSA Level 4 (Strict):
Level 4 further increases security measures by ensuring that all artifacts are stored offline and cryptographically signed by multiple parties. The goal is to protect against advanced supply chain attacks and compromise of signing keys.

