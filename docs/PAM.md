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


## 2FA, PAM and SSH
Setting up Two-Factor Authentication (2FA) with PAM and SSH involves configuring the Pluggable Authentication Modules (PAM) to require additional verification steps beyond the traditional password. Here's a general guide for setting up 2FA with PAM and SSH on a Unix-like system. Note that specific steps may vary depending on your Linux distribution.


- **Configure SSH**:
Make sure your SSH server is installed and configured. The SSH daemon configuration file is often located at /etc/ssh/sshd_config.

- **Install Google Authenticator:**
If you are using Google Authenticator, install the package.
```
# For example, on Debian-based systems
sudo apt-get install libpam-google-authenticator
```
- **Update SSH Daemon Configuration**:
Open your SSH daemon configuration file (/etc/ssh/sshd_config) and make sure the following lines are present:

```
ChallengeResponseAuthentication yes
UsePAM yes
```

- **Configure PAM for SSH**:
Edit the PAM configuration file for SSH. This file is often located at /etc/pam.d/sshd.
```
sudo nano /etc/pam.d/sshd
```
Add the following line at the end of the file to include 2FA:
```
auth required pam_google_authenticator.so
```

- **Restart SSH Service**:
Restart the SSH service to apply the changes.
```
sudo service ssh restart
```
- **Set Up Google Authenticator**:
For Google Authenticator, each user needs to run the google-authenticator command to set up 2FA. This will generate a QR code that users can scan with a mobile authenticator app.
```
google-authenticator
```
Follow the prompts to configure 2FA.

- **Test 2FA**:
Try to log in via SSH to ensure that 2FA is working. You should be prompted for both your password and the 2FA code.

- **Notes**:
  - Depending on your distribution, the PAM module may have a different name or configuration. For example, some distributions use pam_totp.so for 2FA instead of pam_google_authenticator.so.
  - Ensure that the clock on the server and the device generating the 2FA codes are synchronized. Time synchronization is crucial for the correct functioning of time-based one-time passwords (TOTP).
  - Always have a backup method for authentication (e.g., password-based) in case there are issues with the 2FA method.
