# Automatic Private IP Addressing (APIPA)
An Automatic Private IP Addressing (APIPA) address is a self-assigned IP address that a device can automatically assign to itself when it is unable to obtain an IP address from a Dynamic Host Configuration Protocol (DHCP) server. APIPA addresses are typically used in small, local network environments, such as home networks or small office networks, when DHCP server configuration issues or network connectivity problems prevent a device from obtaining a valid IP address.

## Address Range
APIPA addresses are drawn from the reserved IP address range 169.254.0.1 to 169.254.255.254. These addresses are not routable on the public internet and are meant for local communication within a single subnet.
## Automatic Assignment
When a device configured to use DHCP attempts to obtain an IP address but fails to reach a DHCP server or receive a response, it will automatically assign itself an APIPA address within the 169.254.x.x range.
## Local Use
APIPA addresses are only used for local network communication. Devices with APIPA addresses cannot communicate with devices on other networks or the internet.
## Limited Functionality
Devices with APIPA addresses have limited network functionality. They can communicate with other devices on the same local network segment but cannot access resources on other subnets or the internet.
## Conflict Resolution
Devices that assign themselves APIPA addresses will first check the local network to ensure that the chosen address is not already in use. If a conflict is detected, the device will select a different APIPA address.
