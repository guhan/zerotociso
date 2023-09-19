# Wireless Networking
Employs radio waves to transmit signals over a distance. The waves have a frequency between 3Hz and 300Ghz

## Key Concepts
- **Wireless Access Point (WAP)**
- **Site Survey**: checking the presence, strength, and reach of WAPs
- **Captive Portal**: redirects wireless client to a portal access control page

## Wireless Access Points
- **infrastructure mode**: a wireless access point (WAP) is required
- **adhoc mode**: any two wireless devices can communicate without a centralized control authority
- **service set identified (SSID)**: misused to indicate the name of the wireless network
- **basic service set identifier (BSSID)**: in infrastructure mode, it is the MAC address of the base station
  hosting the ESSID. 
- **extended service set identifier (ESSID)**: nsuedame of a wireless network when a base station is used
- **independent service set identifier (ISSID)**: when ad-hoc or peer to peer mode i 
- **wireless channels**: within a wireless signal there are subdivisions called channels. Access points that
  are close to each other should be on different channels.

## Antenna Types
- **Omnidirectional**: Straight pole
- **Directional**:
  - Yagi
  - Cantenna
  - Panel
 
## 802.11* Standards
![802.11](/images/80211.png)

## Wireless Encryption Protocols
- **Wired Equivalent Privacy (WEP)**
  - predefined shared key
  - insecure due to improper Initialization Vector

- **WiFi Protected Access (WPA)**:
  - **WPA-PSK (Pre-Shared Key)**:
    - Also known as WPA-Personal
    - this version uses a shared passphrase (pre-shared key) to authenticate and encrypt communication between devices on the network.
  - **WPA-Enterprise**:
    - This version uses a more robust authentication mechanism, often involving a RADIUS (Remote Authentication Dial-In User Service) server, to authenticate users before granting them access to the network.
- **Temporal Key Integrity Protocol (TKIP)**:
  - TKIP is a specific encryption protocol that was introduced as part of WPA to improve security over the older WEP encryption.
  - TKIP dynamically generates encryption keys for each data packet, making it much harder to crack compared to the static keys used in WEP.

- **Lightweight Extensible Authentication Protocol (LEAP)**: Cisco proprietary alternative to TKIP for WPA
  - _Found to be vulnerable_
- **WPA2**:
  - **Counter Mode Cipher Block Chaining Message Authentication Code Protocol (CCMP)**: uses 128 bit AES key
  - **Extensible Authentication Protocol (EAP)**: authentication framework that lets you add additional authentication technologies
  - **Protected Extensible Authentication Protocol (PEAP)**: encapsulates EAP in a TLS tunnel
  - **WPA2 Enterprise**: uses [RADIUS](RADIUS.md) authentication which protects against password attacks

- **WiFi Protected Setup (WPS)**: security standard for wireless networks
  - insecure to brute force attacks
  - enabled by default on most wireless access points

## Securing Wireless
- Change Administrative password
- Disable broadcasting of the SSID
- MAC filter: only let known MAC addresses join
- Turn off WPS
- Use static IP addresses or DHCP with reservations
- Enable highest authentication and encryption WPA2/3
- Monitor logs from WAPs
- Require all transmissions between wireless clients and WAPs to be encrypted


## Wireless Attacks
- **War Driving**: looking for open wireless networks
- **War Chalking**: physically mark an area with a wireless network
- **Replay**: retransmit captured communications to get some access to the network
- **Exploit Initialization Vector**: if the Initialization Vector is too short or predictable the encryption can be cracked
- **Rogue Access Point**: add a rogue WAP and capture communication
- **Evil Twin**: type of man in the middle attack where rogue WAP intercepts connection requests to the
  real base station
 
## How does wireless manage simultaneous use of limited radio frequencies? 
- **Spread Spectrum**: communication occurs over multiple frequencies at the same time
- **Frequency Hopping Spread Spectrum (FHSS)**: transmits data in series, one frequency at a time is used to minimize
  interference
- **Direct Sequence Spread Spectrum (DSSS)**: all frequencies used in paralled
- **Orthagonal Frequency-Division Multiplexing (OFDM)**: allows for a more tightly compacted transmissions, the signals are perpendicular and do not interfere with each other. Uses less frequencies and has highest throughput. 
