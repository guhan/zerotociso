# Static Analysis
Static analysis, also known as static code analysis or static program analysis, is a software testing technique used to examine the source code or program's structure, without executing it, to find potential issues, security vulnerabilities, or code quality problems. 

## Types of static analysis
- **Linters**: These tools analyze code for stylistic issues, coding conventions, and potential errors. Examples include ESLint for JavaScript and Pylint for Python.
- **Static Code Analyzers**: These tools perform more comprehensive checks for various types of issues, including security vulnerabilities. Examples include SonarQube, Checkmarx, and Fortify.
- **Compiler Warnings**: Many programming languages and compilers provide built-in static analysis capabilities that generate warnings and errors during compilation.

## What is ASH?
AWS Security Helper

- Git
  - git-secrets - Find api keys, passwords, AWS keys in the code
- Python
  - bandit - finds common security issues in Python code.
  - Semgrep - finds common security issues in Python code.
  - Grype - finds vulnerabilities scanner for Python code.
  - Syft - generating a Software Bill of Materials (SBOM) for Python code.
- Jupyter Notebook
  - nbconvert - converts Jupyter Notebook (ipynb) files into Python executables. Code scan with Bandit.
- JavaScript; NodeJS
  - npm-audit - checks for vulnerabilities in Javascript and NodeJS.
  - Semgrep - finds common security issues in JavaScript code.
  - Grype - finds vulnerabilities scanner for Javascript and NodeJS.
  - Syft - generating a Software Bill of Materials (SBOM) for Javascript and NodeJS.
- Go
  - Semgrep - finds common security issues in Golang code.
  - Grype - finds vulnerabilities scanner for Golang.
  - Syft - generating a Software Bill of Materials (SBOM) for Golang.
- C#
  - Semgrep - finds common security issues in C# code.
- Bash
  - Semgrep - finds common security issues in Bash code.
- Java
  - Semgrep - finds common security issues in Java code.
  - Grype - finds vulnerabilities scanner for Java.
  - Syft - generating a Software Bill of Materials (SBOM) for Java.
- Terraform; Cloudformation
  - checkov
  - cfn_nag
  - cdk-nag transforming Cloudformation to CDK, and run cdk-nag
