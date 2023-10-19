# Containers

## Privileged Mode
In Linux, any container in a Pod can enable privileged mode using the privileged (Linux) flag on the security context of the container spec. This is useful for containers that want to use operating system administrative capabilities such as manipulating the network stack or accessing hardware devices.

