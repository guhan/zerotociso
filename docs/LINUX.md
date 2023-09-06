# Linux

## Runlevels
- **Runlevel 0**: Halt or shutdown mode. 
- **Runlevel 1**: Single-user mode. The system starts with minimal services, usually allowing only the root user to log in. It is used for maintenance tasks and troubleshooting.
- **Runlevel 2**: Multi-user mode with _no networking_. This runlevel provides a text-based multi-user environment with minimal services and no networking.
- **Runlevel 3**: Multi-user mode with networking. This runlevel is similar to runlevel 2 but includes networking support, allowing multiple users to log in and use network services.
- **Runlevel 4**: Not used by default. Administrators can define its purpose if needed.
- **Runlevel 6**: Reboot mode.

## Signals
Signals are a way for processes to communicate with each other and with the kernel. Signals are software interrupts that notify a process about events or requests that have occurred. When a signal is sent to a process, the operating system interrupts the normal flow of the process and handles the signal accordingly.

Signals can be used for various purposes, such as terminating a process, pausing and resuming a process, requesting a process to reload its configuration, or sending custom notifications. Some of the common signals in Linux include:

- **SIGHUP (1)**: Sent to indicate that the terminal or connection to the process has been closed. Processes may respond to this signal by reloading their configuration files.
- **SIGINT (2)**: Sent to a process when the user presses the interrupt key (usually Ctrl+C). This signal requests the process to terminate gracefully.
- **SIGKILL (9)**: Sent to forcefully terminate a process. The process cannot ignore or handle this signal and is terminated immediately.
- **SIGUSR1 (10)** and SIGUSR2 (12): User-defined signals that can be used for custom purposes in applications.SIGTERM (15): A generic termination signal sent to request a process to terminate gracefully. Unlike SIGKILL, the process has the opportunity to perform cleanup operations before exiting.
- **SIGCONT (18)**: Sent to resume a previously paused (stopped) process.
- **SIGSTOP (19)**: Sent to pause (stop) a process. The process remains in a suspended state until it receives a SIGCONT signal.

## Filesystem 
The Linux file system layout is a hierarchical structure that organizes files and directories on a Linux-based operating system. While there are several variations among different Linux distributions, most adhere to a common file system hierarchy standard, often referred to as the Filesystem Hierarchy Standard (FHS). The FHS defines a common layout to ensure consistency and compatibility across Linux distributions. Here's a simplified overview of the key directories and their purposes in the Linux file system layout:

- **/** (Root Directory): The root directory is the top-level directory in the file system hierarchy. It contains all other directories, files, and system files required for the operating system to function.
- **/bin** (Binary Programs): This directory holds essential binary executables (commands) that are required for system recovery and maintenance. Common system commands, such as ls (list files), cp (copy files), and mv (move files), are typically located here.
- **/boot** (Boot Files): The /boot directory contains the kernel and bootloader configuration files necessary for the system to boot.
- **/dev** (Device Files): Device files represent physical and virtual devices and peripheral hardware components. For example, /dev/sda represents the first hard drive, and /dev/null is a special file for discarding data.
- **/etc** (Configuration Files): Configuration files and directories for system-wide and application-specific settings are stored here. System administrators often modify files in /etc to configure the behavior of various services and applications.
- **/home** (User Home Directories): Each user typically has a subdirectory under /home where their personal files and settings are stored.
- **/lib** and **/lib64** (Shared Libraries): These directories contain shared libraries (dynamic link libraries) that are essential for running programs and applications.
- **/media** and **/mnt** (Mount Points): These directories are used for mounting removable devices (such as USB drives and optical disks) and temporarily mounting filesystems, respectively.
- **/opt** (Optional Software): Some software packages install in this directory. It's often used for third-party or optional software.
- **/proc** (Process Information): The /proc directory provides information about running processes and system configuration. It's a virtual filesystem that allows access to kernel and process-related data.
- **/root** (Root User Home): The home directory for the system's root user.
- **/sbin** (System Binaries): Similar to /bin, /sbin contains essential system commands, but these are typically intended for system administration tasks and require superuser privileges to execute.
- **/srv** (Service Data): This directory is used to store data files related to services provided by the system. It is often used for web server data, among other things.
- **/tmp** (Temporary Files): Temporary files created by various processes and users are stored here. The /tmp directory is usually cleared upon system reboot.
- **/usr** (User Programs and Data): The /usr directory contains user-level programs, libraries, documentation, and data files. It is often split into subdirectories like /usr/bin, /usr/lib, /usr/share, and so on.
- **/var** (Variable Data): This directory contains variable data files, including log files (/var/log), spool directories (/var/spool), and other files that may change in size over time.
