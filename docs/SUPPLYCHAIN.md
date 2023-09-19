# Supply Chain Compliance


## Software Bill of Materials (SBOM)
A software bill of materials is a document that contains all the items required to build a particular piece of software. 


### CycloneDX
Produces a format for an SBOM

### Vulnerability Expolitable Exchange (VEX)
VEX contains information about how exploitable a particular vulnerability in the SBOM is. 




### in-toto
open-source framework and specification designed to ensure the integrity and security of software supply chains

https://github.com/in-toto/docs/blob/v0.9/in-toto-spec.pdf

1. Software Supply Chain Transparency: In-toto allows stakeholders to trace the entire software supply chain to ensure that each step in the process was performed securely and as expected.
2. Metadata Signing: In-toto uses cryptographic signatures to sign and verify metadata at each step in the supply chain. This ensures that each step is tamper-evident, and any unauthorized modifications are detectable.
3. Linking Steps: In-toto provides mechanisms to link each step in the supply chain to the previous and subsequent steps, creating a chain of trust.
4. Minimal Toto Recipes: In-toto uses "Toto Recipes" to specify the expected sequence of steps in the supply chain. These recipes are simple and minimal, making them easy to read, write, and verify.
5. Flexibility and Customization: In-toto allows for flexibility and customization, enabling organizations to tailor the framework to their specific software supply chain requirements.













