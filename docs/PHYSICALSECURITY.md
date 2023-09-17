# Physical Security 

## Key Concepts
- **Secure facility plan**: Outlines the security needs of your organization and emphasizes methods or
  mechanisms to employ to provide security.
- **Technology convergence**: tendency of various technologies to evolve and _merge_ over time


## Physical Security Plan
- Secure Site selection
- Perimeter Security Controls
  - Fences
  - Gates
  - Turnstiles
  - Mantraps
- Lighting
- Security Guards and Dogs
- Internal Controls
  - Locks
  - Badges
  - Motion Detectors
  - Intrusion Alarms
  - Secondary Verification (CCTV)
  - Environment and Life safety


## Site Selection
- Cost
- Size
- Location
- Security
- Visibility
- Natural Disasters
- Design of facility
  - fire rating
  - HVAC
  - Ceilings/Floors
  - Intrusion protection
  - EMR
 
### Crime prevention through Environmental Design (CPTED)
Crime Prevention Through Environmental Design (CPTED) is a theory and practice that focuses on altering the physical and social environment in order to reduce opportunities for crime and enhance the overall safety of a community or space. The basic idea behind CPTED is that by designing and arranging the environment in certain ways, the likelihood of criminal behavior can be minimized or deterred.

Key principles of Crime Prevention Through Environmental Design include:

- Natural Surveillance: Designing spaces in a way that maximizes visibility, making it easier for people to see and be seen. This can discourage criminal activity as potential wrongdoers are less likely to act if they believe they are being watched.
- Natural Access Control: Designing entrances, exits, and pathways in a way that controls and directs the flow of people. By making it clear where people are supposed to go and where they're not supposed to go, unauthorized access can be reduced.
- Territorial Reinforcement: Establishing a sense of ownership and territorial identity for spaces. This can be achieved through landscaping, signage, and other design elements that communicate that the space is cared for and monitored.
- Maintenance and Management: Keeping spaces well-maintained and managed signals that the environment is actively monitored and cared for. Neglected spaces are often more attractive to criminal activity.
- Target Hardening: Implementing physical measures to make spaces less vulnerable to crime. This could involve things like improved lighting, security cameras, locks, and alarms.
- Defensible Space: Designing spaces that allow residents or users to have some control over their surroundings. This can create a sense of responsibility and encourage people to actively protect the area.

## Physical Security Controls

### Order of Importance
1. Deterrance
2. Denial
3. Detection
4. Delay

### Securing a wiring closet
Securing a wiring closet is essential to protect sensitive network equipment, data, and infrastructure from unauthorized access and tampering. Here are some steps you can take to secure a wiring closet effectively:

#### Physical Access Control:
- Install a sturdy lock on the door to the wiring closet. Use a high-security lock or electronic access control system for added protection.
- Restrict access to authorized personnel only. Provide keys or access cards to those who need to enter the closet.
- Implement a sign-in/sign-out process to keep track of who enters the closet and when.
- Consider using biometric access systems (fingerprint or retina scanners) for an additional layer of security.

#### Surveillance:
- Install security cameras outside the wiring closet to monitor access and activity.
- Position cameras strategically to capture any attempts at unauthorized entry.

#### Environmental Controls:
- Maintain appropriate temperature and humidity levels in the wiring closet to prevent equipment damage.
- Use environmental monitoring systems to alert you to any abnormal conditions.

#### Equipment Organization:
- Keep network equipment, cables, and wires organized to quickly identify any tampering or unauthorized changes.
- Use cable management solutions to prevent cables from being tampered with or accidentally disconnected.

#### Secure Racks and Cabinets:
- Use locked racks or cabinets to house networking equipment, servers, and switches.
- Ensure that the racks and cabinets themselves are securely anchored to the floor or wall.

#### Alarms and Sensors:
- Install intrusion detection systems that trigger alarms if unauthorized access is detected.
- Use vibration sensors or contact sensors on doors and panels to detect any tampering attempts.

#### Restricted Network Ports:
- Disable unused network ports to prevent unauthorized devices from being connected to the network.

#### Documentation:
- Keep accurate records of authorized personnel who have access to the closet.
- Maintain an inventory of all equipment in the closet to quickly identify missing or tampered items.

#### Regular Inspections:
- Conduct regular inspections of the wiring closet to ensure that all security measures are in place and functioning as intended.

#### Employee Training:
- Train employees on the importance of security protocols and the proper use of the wiring closet.
- Teach them how to recognize and report any suspicious activity.

#### Backup and Redundancy:
- Regularly back up network configurations and data in case of tampering or data loss.
- Consider implementing redundancy to minimize the impact of a potential breach.

#### Vendor Management:
- Vet and monitor any third-party vendors or contractors who may require access to the closet.


### Smartcards
- ID token containing an Integrated Circuit
- A processor IC card
- An IC card with an ISO 7816 interface

### Memory Cards
Machine readable ID cards with a magnetic strip

### Proximity Readers
Passive, field powered or a transponder which is designed to be worn by the authorized bearer. 
- Radio Frequency Identification (RFID) is one class of these

### Intrustion Detection Systems
- Burglar Alarms
- Heat sensors
- Motion detectors
- _Need a heartbeat sensor to ensure that power or communication is not cut_

### Emanation Security
Many electrical devices emanate electrical signals or radiation that can be intercepted by unauthorized individuals. 
- TEMPEST countermeasures (Faraday cages, white noise, and control zones) were developed to protect against these attacks

## Media Storage Facilities 
- Inventory Management: Keep an inventory of all media items stored in the facility to quickly identify any missing items.
- Use hash based integrity system


## Restrooms
Keep these in public areas so that privileged access is not required

## Power
- **Uinteruptible Power Supply (UPS)**: self charging battery
- **Surge Protector**: has a fuse that blows if power levels change dramatically

## Noise 
electromagnetic interference or EMI
- **Common Mode Noise**: difference in power between the hot and ground
- **Traverse Mode Noise**: difference in power between hot and neutral wire

Radio Frequency Interference(RFI)
- Protect by using proper grounding, shielding all cables, and limiting exposure to EMI and RFI sources

## Heating, Ventilation and Air Conditioning (HVAC)
Temperature should be between 60 and 75 degrees 
Humidity from 40-60 percent

## Water
Water and electricity don't mix, any leaks will cause damage

## Fire
- Fire Triangle: Flamable Material, Heat, Oxygen are the three corners

| Class | Type | Suppression Material |
| ----- | ---- |----------------------|
|A|Common Combustibles|Water, Soda acid|
|B|Liquids|C02, halon*, soda acid |
|C|Electrical|C02, halon*|
|D|Metal|Dry Powder|

### Fire Detection Systems
- Fixed Temperature Detection
- Rate of Rise detection
- Flame actuated
- Smoke Actuated

### Water Suppression Systems
- **Wet Pipe**: alwasy full of water
- **Dry Pipe**: has compessed air and pipe fills with air
- **Deluge System**: larger pipes and more water (sprinkler), deluge valve keeps pipes dry
- **Preeaction System**: Fills with water and then when fire hits sprinker activates.


### Gas Discharge System
More effective than water dischage, but are dangerous for humans. 

Halon: starves fire of oxygen by disrupting the chemical reaction between oxygen and combustible materials. 

## Static Electricity
- Generally occurs in low humidity
