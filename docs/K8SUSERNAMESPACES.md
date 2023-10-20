# User namespaces for Pods
A process running as root in a container can run as a different (non-root) user in the host.

- A pod can opt-in to use user namespaces by setting the pod.spec.hostUsers field to false.

- The runAsUser, runAsGroup, fsGroup, etc. fields in the pod.spec always refer to the user inside the container.

- The valid UIDs/GIDs when this feature is enabled is the range 0-65535. This applies to files and processes (runAsUser, runAsGroup, etc.).
