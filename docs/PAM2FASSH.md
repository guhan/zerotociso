# PAM, 2FA, and SSH
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
