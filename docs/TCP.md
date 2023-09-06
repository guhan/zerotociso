# TCP

## What is a three-way handshake?
- A: SYN, initial sequence number
- B: SYN-ACK, initial sequence number 
- A: ACK, increments B’s ISN

## How are TCP connections closed?
- FIN: start the process for a graceful shutdown with a 4 way ACK
- RST: abrubt close

## What is in a TCP header?
- 20 to 60 bytes long
