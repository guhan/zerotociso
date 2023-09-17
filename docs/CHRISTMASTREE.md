# Christmas Tree
A Christmas Tree attack, also known as a Christmas Tree packet, is a network-based cyberattack that involves sending a specially crafted TCP (Transmission Control Protocol) packet with various TCP flags set to create a pattern resembling a decorated Christmas tree. This attack is primarily a form of port scanning and reconnaissance used by attackers to identify open ports and potentially vulnerable services on a target system.

The term "Christmas Tree" is derived from the visual appearance of the TCP packet, which resembles a Christmas tree with its many "lights" or flags turned on. Specifically, in a Christmas Tree packet, the following TCP flags are set:

- URG (Urgent): Indicates that the urgent pointer field is significant.
- ACK (Acknowledgment): Indicates that the acknowledgment field is significant.
- PSH (Push): Instructs the receiving system to deliver data to the application as soon as possible without buffering.
- FIN (Finish): Indicates that the sender has finished sending data.
- SYN (Synchronize): Initiates a connection establishment with the target.
- RST (Reset): Can be used to reset an established connection or indicate an error condition.

## How does a Christmas tree attack work?
A Christmas Tree packet is typically sent with random or sequential TCP port numbers to probe the target system for open ports and services. When the target system receives a Christmas Tree packet, it may respond differently based on how it interprets the unusual combination of TCP flags. Here are some possible responses:

- If a target system responds with a RST packet, it indicates that the port is closed or the service is not listening.
- If a target system does not respond at all, it may indicate that the port is open, and the system is dropping the Christmas Tree packet silently.
- If a target system responds with an acknowledgment (ACK) packet, it may indicate that the port is open, and the service is actively listening.
