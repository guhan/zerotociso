# Pluggable Authentication Modules (PAM)
PAM is a framework used on Unix-like systems to centralize and standardize the authentication mechanism. It provides a way to develop authentication-related services independently of the application using them, making it easier to manage and configure authentication across different applications.

When it comes to SSH, PAM is commonly used to handle the authentication process. Here's how it works in the context of SSH:

## User Authentication
When a user attempts to log in to a system using SSH, the SSH server interacts with the PAM subsystem to authenticate the user.

## Pluggable Modules
PAM allows administrators to configure authentication policies through pluggable modules. These modules are small, self-contained units that can be stacked to form a chain of authentication actions.

## Authentication Actions
PAM modules can perform various authentication actions, such as checking passwords, verifying user identity through two-factor authentication, and more. Each action is typically handled by a specific PAM module.

## Configuration File:
The configuration for PAM is specified in the /etc/pam.d/ directory. For SSH, the relevant configuration file is often /etc/pam.d/sshd.

## Authentication Process
When a user tries to log in via SSH, the SSH server consults the PAM configuration for SSH in /etc/pam.d/sshd. This configuration file specifies which PAM modules to use and in what order.

## Module Stacking
PAM allows administrators to stack multiple modules for a single action. For example, a common setup might involve stacking modules for password authentication, two-factor authentication, account validation, and more.

## Success or Failure
Each PAM module returns a status upon completion (success, failure, or error). The authentication process succeeds only if all modules in the stack succeed.


