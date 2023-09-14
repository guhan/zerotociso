# Ports

## Types 
- 2^16 or 65536 total
- 0 to 1023: service, well known, or privileged ports
 
- 1024 to 49151: registered software ports. [IANA](https://wwwiana.org) lets you register the port with them.
- 49152 to 65535: random or dynamic ports

## Status
- Open: accessible and something responds
- Closed: accessible but nothing responds
- Filtered: not accessible

## Services
- 20 FTP Data: Used for FTP data transfer.
- 21 FTP Control: Used for FTP control commands.
- 22 SSH
- 23 Telnet
- 25 SMTP
- 53 DNS: Used for domain name resolution.
- 80 HTTP
- 110 POP
- 123 NTP: Used for time synchronization between computers.
- 137 NetBIOS Name Service
- 138 NetBIOS Datagram Service
- 139 NetBIOS Session Service
- 143 IMAP
- 161 SNMP: Used for network monitoring and management
- 389 LDAP: Used for directory services and authentication.
- 444 HTTPS
- 445 SMB: Used for file and printer sharing in Windows networks (CIFS is a dialect of SMB).
- 465 SMTPS: Used for secure email communication over SMTP.
- 990 FTPS: Used for secure FTP connections.
