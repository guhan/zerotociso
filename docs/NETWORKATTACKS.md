# Network Attacks





## What is the difference between a smurf and fraggle attack?
A "Fraggle Attack" is a type of Distributed Denial of Service (DDoS) attack that is similar to the better-known Smurf Attack. Both Fraggle and Smurf attacks exploit a vulnerability in the Internet Control Message Protocol (ICMP) and the User Datagram Protocol (UDP) to flood a victim's network and overwhelm its resources, causing disruption.

Here's how a Fraggle Attack works:

- **Amplification**: The attacker sends a large number of UDP (ports 7 and 19) or ICMP echo request packets to a network's broadcast address, which is a special address that sends packets to all devices on a specific network.
- **Spoofing**: The source IP address in these packets is spoofed to be the victim's IP address. This means the responses from the network will be directed towards the victim's IP.
- **Network Response**: The network devices, unaware that the IP address is spoofed, respond by sending echo replies to the victim's IP address. These responses are often much larger than the original request packets, thus amplifying the attack's impact.
- **Overwhelm**: With a large number of these amplified responses directed at the victim's IP, the victim's network becomes overwhelmed with traffic, leading to a denial of service for legitimate users and services.

Fraggle Attacks are quite similar to Smurf Attacks, which exploit the same vulnerability but use ICMP packets (Ping requests) instead of UDP packets. In both cases, the attacker takes advantage of the broadcast nature of the network and the amplification of responses to create a significant amount of traffic targeting the victim.

To protect against Fraggle and Smurf attacks, network administrators can implement various measures, including:

- **Filtering**: Configure network devices to prevent external traffic from using the network's broadcast address.
- **Anti-Spoofing Measures**: Employ ingress and egress filtering to prevent the spoofing of IP addresses within the network.
- **Rate Limiting**: Implement rate limiting for ICMP and UDP traffic to prevent excessive requests from any single source.
- **Firewalls and Intrusion Prevention Systems**: Utilize firewalls and intrusion prevention systems to detect and mitigate unusual traffic patterns indicative of such attacks.
- **Network Design**: Segregate network segments to limit the propagation of broadcast traffic.
