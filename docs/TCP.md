# Transmission Control Protocol (TCP)
Offers reliable, connection-oriented communication, ensuring that data is delivered accurately and in the correct order. TCP manages flow control, error detection, and retransmission of lost or corrupted packets.
  - Packets are called _Segment_
  - Full Duplex

## TCP Packet
![TCP Packet](/images/TCP.png)

## What is a three-way handshake?
- A: SYN, initial sequence number
- B: SYN-ACK, initial sequence number 
- A: ACK, increments B’s ISN

## How are TCP connections closed?
- FIN: start the process for a graceful shutdown with a 4 way ACK
- RST: abrubt close

## What is in a TCP header?
- 20 to 60 bytes long
