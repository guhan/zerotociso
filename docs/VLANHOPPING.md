# VLAN Hopping
VLAN hopping is a network security vulnerability and attack technique in which an **attacker gains unauthorized access to traffic in different Virtual LANs (VLANs)** within a switched network. VLAN hopping occurs when an attacker exploits weaknesses in the configuration or operation of network switches to move traffic between VLANs to which they do not have legitimate access. This attack can potentially expose sensitive data and compromise network security.

There are two common methods of VLAN hopping:

- **Double-Tagging** (VLAN Double-Encapsulation):
This method typically targets a switch that incorrectly processes or trusts 802.1Q tagged frames.
The attacker sends frames with two or more 802.1Q tags, making it appear as if the frame has traversed multiple VLANs. The outer tag represents the attacker's VLAN, and the inner tag represents the target VLAN.
If the target switch incorrectly processes the frame, it may forward it to the target VLAN, allowing the attacker to access the traffic.

- **Switch Spoofing** (MAC Spoofing):
In this method, the attacker spoofs the Media Access Control (MAC) address of a device within the target VLAN.
The attacker then sends frames with this spoofed MAC address to the switch.
The switch, thinking the frames belong to the legitimate device, forwards them to the target VLAN.

## How do you protect against VLAN hopping?
VLAN hopping can have serious security implications because it allows attackers to bypass network segmentation, potentially gaining access to sensitive data or compromising the security of other VLANs. To mitigate VLAN hopping attacks, network administrators can take the following measures:

- **Disable Unused Ports**: Disable unused switch ports to prevent potential attackers from plugging into the network.
- **Enable Port Security**: Implement port security features that restrict the number of MAC addresses allowed on a port and bind specific MAC addresses to the port.
- **Disable Trunking on Access Ports**: On access ports (ports connected to end-user devices), disable trunking and allow only untagged frames, preventing attackers from sending multiple tagged VLANs.
- **VLAN Access Control Lists (VACLs)**: Use VACLs to control traffic between VLANs and apply filtering rules to restrict unauthorized traffic.
- **Protect Against Double-Tagging**: Configure switches to properly handle and discard frames with multiple VLAN tags, preventing double-tagging attacks.
- **Implement Private VLANs**: Private VLANs (PVLANs) restrict communication between devices within the same VLAN, providing an additional layer of isolation and security.
- **Regularly Update Switch Firmware**: Keep switch firmware up to date to benefit from security patches and fixes.
- **Security Monitoring**: Continuously monitor network traffic and use intrusion detection systems (IDS) to detect and respond to unusual VLAN-related activities.
