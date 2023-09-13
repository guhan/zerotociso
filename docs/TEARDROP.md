# Teardrop Attack
A Teardrop attack is a type of Denial of Service (DoS) attack that exploits vulnerabilities in the reassembly of fragmented packets in a target system's network stack. It was first discovered in the late 1990s and primarily affected older versions of the Windows operating system. Modern operating systems and network equipment are typically not vulnerable to Teardrop attacks due to security improvements.

Here's how a Teardrop attack works:

- **Packet Fragmentation**: In IP (Internet Protocol), large data packets are often fragmented into smaller packets for transmission across a network. Each smaller packet, known as a "fragment," contains a portion of the original data and has a unique offset value to help the receiving system reassemble them correctly.
- **IP Identification Field**: Each IP packet has an identification field that is used to associate fragments from the same original packet. Fragments with the same identification value are considered part of the same packet.
- **Teardrop Attack**: In a Teardrop attack, an attacker sends a series of IP fragments to a target system, each with deliberately overlapping offset values or incorrect offset values that cause the target system to become confused when attempting to reassemble them.
- **Packet Reassembly Vulnerability**: Vulnerable systems may have flaws in their packet reassembly code that cannot handle the overlapping or incorrectly ordered fragments properly. As a result, the system may crash, freeze, or become unresponsive, leading to a denial of service condition.
