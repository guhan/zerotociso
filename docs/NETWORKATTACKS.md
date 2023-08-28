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
