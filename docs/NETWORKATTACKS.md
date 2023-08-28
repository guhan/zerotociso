# Network Attacks



## What are syn cookies?
SYN cookies, short for "Synchronization Cookies," are a technique used in computer networking and 
internet security to mitigate the risk of Distributed Denial of Service (DDoS) attacks and protect 
against SYN flood attacks. SYN flood attacks are a type of attack where an attacker sends a large 
number of SYN (synchronize) requests to a target server, overwhelming its resources and potentially 
causing it to become unavailable.

Here's how SYN cookies work:

- **TCP Three-Way Handshake**: In a normal TCP connection, a three-way handshake is performed between a client 
and a server. The client sends a SYN packet to the server, the server responds with a SYN-ACK packet, 
and the client acknowledges with an ACK packet. This establishes a connection.
- **SYN Flood Attack**: In a SYN flood attack, an attacker sends a large number of SYN packets
to a target server but never responds to the SYN-ACK packets sent by the server. This can lead to the
server maintaining a large number of half-open connections and eventually exhausting its resources,
making it unable to handle legitimate traffic.
- **SYN Cookies**: To mitigate SYN flood attacks, servers can use SYN cookies. When a server receives a
SYN packet from a client, it generates a SYN cookie based on the client's IP address, port, and a
secret value. The server then sends the SYN-ACK packet to the client with the SYN cookie in place of
the initial sequence number. The client responds with an ACK packet that includes the SYN cookie.
- **Verification and Connection Setup**: Upon receiving the ACK packet with the SYN cookie, the server
can use the information in the SYN cookie to reconstruct the initial sequence number and verify that
the connection request is legitimate. If the connection is valid, the server establishes the connection
as usual.

The advantage of SYN cookies is that they allow the server to maintain state information for
incoming connection requests without keeping track of a large number of half-open connections. Since the
initial sequence number is encoded within the SYN cookie, the server can verify the legitimacy of
the connection request without keeping the connection state in memory until the ACK packet is received.


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
