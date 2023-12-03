# Side Channel Attacks
Side-channel attacks are a class of attacks that exploit information leaked during the execution of a cryptographic algorithm or system. These attacks don't target the inherent weaknesses of the cryptographic algorithms themselves but rather focus on unintended information leakage, often through the physical implementation of the system or the execution environment. The main idea is to gather information from side channels, such as power consumption, electromagnetic emanations, timing variations, or other observable phenomena, to deduce secret information.

## Power Analysis Attacks
Power analysis attacks involve analyzing the power consumption of a device during the execution of cryptographic operations. Different cryptographic operations and data values can lead to distinct power consumption patterns. Techniques include simple power analysis (SPA) and differential power analysis (DPA).

## Timing Attacks
Timing attacks exploit variations in the time taken to execute cryptographic operations. By measuring the time it takes for certain computations, an attacker may gain information about the secret key. A well-known example is a "cache timing attack."

## Electromagnetic Attacks
Electromagnetic attacks focus on analyzing the electromagnetic radiation emitted by electronic devices during cryptographic operations. By capturing and analyzing these emissions, attackers may deduce sensitive information.

## Acoustic Attacks
Acoustic attacks involve analyzing sound emissions produced by electronic devices during cryptographic operations. Vibrations caused by the movement of components can reveal information about the internal state of the device.

## Fault Injection Attacks
Fault injection attacks involve intentionally introducing faults into the execution of a cryptographic algorithm. By manipulating the input or the environment to induce errors, attackers may observe the system's response to deduce information about the secret key.

## Cache-based Attacks
Cache-based attacks exploit variations in the time it takes to access data stored in the cache memory. By observing the timing differences, an attacker may gain insights into the operations being performed.

## Software-Based Side Channels
Some side-channel attacks exploit software-related information leaks, such as variations in execution time, cache behavior, or memory access patterns.
