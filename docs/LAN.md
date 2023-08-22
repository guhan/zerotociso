# LAN Technologies
Local Area Network (LAN) technologies are used to connect devices within a limited geographical area, such as a home, office, or campus. There are several LAN technologies that vary in terms of data transfer rates, transmission media, and architectural features. Here are some common LAN technologies:

- **Ethernet**:
Ethernet is one of the most widely used LAN technologies. It uses various transmission speeds, such as 10 Mbps (10BASE-T), 100 Mbps (Fast Ethernet), 1 Gbps (Gigabit Ethernet), 10 Gbps, 25 Gbps, 40 Gbps, and 100 Gbps. Ethernet uses twisted-pair cables (e.g., Cat 5e, Cat 6, Cat 6a) or fiber optics for data transmission.

- **Wi-Fi (Wireless LAN)**:
Wi-Fi technology enables wireless communication between devices using radio frequencies. It's commonly used for connecting laptops, smartphones, tablets, and IoT devices. Wi-Fi operates in various standards, such as 802.11a/b/g/n/ac/ax, offering different data rates and coverage ranges.

- **Token Ring**:
Token Ring is an older LAN technology that uses a token-passing protocol. Devices are connected in a
ring topology, and data is transmitted using tokens. The device with the token can transmit. It was less common than Ethernet and
is mostly considered a legacy technology.

- **Fiber Distributed Data Interface (FDDI)**:
FDDI is a high-speed LAN technology primarily used in corporate environments. It uses fiber optic cables
and a dual ring topology to provide redundancy and fault tolerance.

- **Powerline Communication (PLC)**:
PLC technology allows data transmission over electrical power lines. It can provide networking capabilities
by using existing power infrastructure.

- **Infrared Data Association (IrDA)**:
IrDA is a short-range wireless communication technology that uses infrared light to transmit data
between devices. It was commonly used for wireless communication between devices like laptops and printers.

- **Bluetooth**:
Bluetooth is a short-range wireless technology commonly used for connecting devices like smartphones,
keyboards, mice, and speakers. While it's not typically used for traditional LANs, it enables personal
area networks (PANs) within short distances.

- **HomePlug**:
HomePlug is a technology that uses the electrical wiring in a building to create a LAN. It's often used
for connecting devices in a home or small office environment.

- **LocalTalk**:
LocalTalk was Apple's proprietary LAN technology used in older Macintosh computers. It used a serial cable to connect devices.
These are some of the LAN technologies that have been used over the years

## LAN media access technologies
LAN (Local Area Network) media access technologies govern how devices on a network share and access 
the network's communication medium. These technologies ensure efficient and fair usage of the network 
resources. Here are some common LAN media access technologies:

- **Carrier Sense Multiple Access/Collision Detection (CSMA/CD)**:
Used in Ethernet networks, CSMA/CD is a contention-based media access method. Before transmitting data, a
device listens for carrier signals to ensure the channel is clear. If a collision is detected
(two devices transmitting simultaneously), both devices stop transmitting, introduce a random
backoff delay, and then reattempt transmission.
- **Carrier Sense Multiple Access/Collision Avoidance (CSMA/CA)**:
Used in Wi-Fi networks, CSMA/CA is similar to CSMA/CD but designed to avoid collisions due to the
"hidden node" problem. Devices listen for carrier signals and announce their intent to transmit before
sending data. This helps avoid collisions caused by devices that can't hear each other.

- **Token Passing**:
Token passing is used in Token Ring networks. A special data packet called a "token" circulates
the network. A device can only transmit data when it has possession of the token. Once data
transmission is complete, the token is passed to the next device in the ring.

- **Polling**:
In polling, a central controller (e.g., hub, switch) queries devices in sequence, allowing them
to transmit data when polled. This method can be efficient but requires a dedicated controller.

- **Demand Priority**:
Used in Fiber Distributed Data Interface (FDDI) networks, demand priority assigns different
priority levels to devices. Devices with higher priority have a better chance of accessing the medium.

- **Random Access Protocols**:
These protocols allow devices to transmit whenever they want. Examples include Aloha, Slotted Aloha, and
the Ethernet's CSMA/CD.

- **Time Division Multiple Access (TDMA)**:
In TDMA, time is divided into slots, and devices are assigned specific time slots for transmission.
TDMA is commonly used in cellular networks.

- **Frequency Division Multiple Access (FDMA)**:
FDMA assigns different frequency bands to different devices, allowing simultaneous transmission by
dividing the frequency spectrum.

- **Code Division Multiple Access (CDMA)**:
CDMA assigns unique codes to devices, allowing them to transmit data simultaneously but with
different codes. This technology is often used in cellular and wireless networks.

- **Orthogonal Frequency Division Multiplexing (OFDM)**:
OFDM divides the frequency spectrum into multiple subcarriers that can transmit data simultaneously.
This technology is used in Wi-Fi and other high-speed wireless systems.
