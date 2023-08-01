# Linux

## Runlevels
- Runlevel 0: Halt or shutdown mode. 
- Runlevel 1: Single-user mode. The system starts with minimal services, usually allowing only the root user to log in. It is used for maintenance tasks and troubleshooting.
- Runlevel 2: Multi-user mode with no networking. This runlevel provides a text-based multi-user environment with minimal services and no networking.
- Runlevel 3: Multi-user mode with networking. This runlevel is similar to runlevel 2 but includes networking support, allowing multiple users to log in and use network services.
- Runlevel 4: Not used by default. Administrators can define its purpose if needed.
- Runlevel 6: Reboot mode.

## Signals
Signals are a way for processes to communicate with each other and with the kernel. Signals are software interrupts that notify a process about events or requests that have occurred. When a signal is sent to a process, the operating system interrupts the normal flow of the process and handles the signal accordingly.

Signals can be used for various purposes, such as terminating a process, pausing and resuming a process, requesting a process to reload its configuration, or sending custom notifications. Some of the common signals in Linux include:

- SIGHUP (1): Sent to indicate that the terminal or connection to the process has been closed. Processes may respond to this signal by reloading their configuration files.
- SIGINT (2): Sent to a process when the user presses the interrupt key (usually Ctrl+C). This signal requests the process to terminate gracefully.
- SIGKILL (9): Sent to forcefully terminate a process. The process cannot ignore or handle this signal and is terminated immediately.
- SIGUSR1 (10) and SIGUSR2 (12): User-defined signals that can be used for custom purposes in applications.SIGTERM (15): A generic termination signal sent to request a process to terminate gracefully. Unlike SIGKILL, the process has the opportunity to perform cleanup operations before exiting.
- SIGCONT (18): Sent to resume a previously paused (stopped) process.
- SIGSTOP (19): Sent to pause (stop) a process. The process remains in a suspended state until it receives a SIGCONT signal.
