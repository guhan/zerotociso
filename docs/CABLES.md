# Cables

## Key Concepts
- **Baseband**: only transmit a single signal at one time
- **Broadband**: mutliple signals simultaneously

## Notation
XXBaseZZ
- XX is the speed in Mbps
- ZZ is the max distance in _100 meter_ increments

```
10Base2
```
10 Mbps for 200 meters max distance

```
1000BaseT
```
1 Gbps for 100 meters max distance

## Coaxial Cable
- center core of copper surrounded by insulation and then surrounded by conductive braided shielding
- the two layers act as independent conductors
- requires use of segment terminators
- Two types:
  - **Thinnet**: 10Base2 185 meters and 10Mbps
  - **Thicknet**: 10Base5 500 meters and 10Mbps
- Problems:
  - bending caused breakage of copper core
  - can't deply beyond 185 meters
  - not properly terminating the ends with a 50 ohm resistor
  - not grounding at least one end of the coax cable
 
## Twisted pair
- Very thin and flexible
- four  pairs of wires that are twisted around each other and sheathed in PVC
- **Shielded Twisted Pair (STP)**:foil around the wires that protects against EMI
- **Unshielded Twisted Pair (UTP)**:no foil

### Types of UTP
| UTP Category | Throughput | Notes |
|----|----|----|
|Cat 1|Voice ony|usable only by modems |
|Cat 2|4 Mbps|host to terminal for mainframes |
|Cat 3|10 Mbps|10BaseT networks |
|Cat 4|16 Mbps |used by Token ring networks |
|Cat 5|100 Mbps |10BaseTX, FDDI, and ATM networks |
|Cat 6|1000 Mbps |high speed networks |
|Cat 7|10 Gbps |used on 10Gigabit networks |

### Problems with UTP
- wrong category of UTP used
- longer than max length of 100 meters
- used in areas with significant interference


## 5-4-3 Rule
The "5-4-3 rule" refers to a guideline used in early Ethernet networking to determine the maximum number 
of repeaters and segments allowed in a specific network topology. This rule was applicable to Ethernet 
networks using the 10BASE5 (Thicknet) and 10BASE2 (Thinnet) standards. These standards have largely 
been replaced by newer Ethernet technologies, but the rule is still a historical concept in networking.

The rule is as follows:

- 5: The maximum number of network segments.
- 4: The maximum number of repeaters (or populated segments).
- 3: Out of the four populated segments, only three can contain user devices (computers, devices).
