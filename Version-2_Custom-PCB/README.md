# JF Audio Version 2 - Custom PCB

## Overview

Version 2 of JF Audio is the second major revision of my portable Bluetooth speaker project. This version builds upon the working Version 1 prototype by replacing the breadboard-based construction with a custom PCB and a more integrated rechargeable power system.

Version 1 successfully demonstrated the basic Bluetooth speaker architecture, but the breadboard, jumper wires, AA battery system, and modified food-container enclosure introduced limitations in size, organization, reliability, and usability.

Version 2 was designed to address these limitations while providing experience with PCB schematic capture, PCB layout and routing, component selection, design-rule checking, PCB manufacturing, rechargeable battery systems, and hardware integration.

---

## Design Goals

- Replace the breadboard and jumper-wire construction with a custom PCB
- Reduce the amount of internal wiring
- Improve electrical and mechanical organization
- Implement a rechargeable lithium-ion battery system
- Improve power distribution and grounding
- Create more reliable electrical connections
- Use a dedicated plastic electronics enclosure
- Improve the overall appearance and portability of the speaker
- Gain experience designing and manufacturing a custom PCB
- Apply lessons learned from Version 1

---

## Major Improvements Over Version 1

| Version 1 | Version 2 |
|---|---|
| Breadboard construction | Custom PCB |
| Large number of jumper wires | PCB traces and dedicated connectors |
| 4x AA battery pack | Rechargeable lithium-ion battery |
| No integrated charging | Rechargeable power system |
| Modified food container | Dedicated plastic enclosure |
| Prototype-oriented construction | More permanent hardware |
| Large internal wiring footprint | More compact electrical layout |

---

## System Architecture

Version 2 maintains the same general Bluetooth audio architecture demonstrated successfully in Version 1 while redesigning the power system and physical implementation.

The major sections of the system are:

1. Rechargeable battery system
2. Power management and 5 V supply
3. Bluetooth audio receiver
4. Stereo audio amplifier
5. Left and right speakers
6. Custom PCB
7. External power control

### General Signal Flow

`Bluetooth Audio → Audio Amplifier → Left/Right Speakers`

### General Power Flow

`Rechargeable Li-ion Battery → Power/Charging System → 5 V Electronics Supply → Bluetooth Receiver + Audio Amplifier`

---

## Custom PCB

One of the primary improvements introduced in Version 2 is the replacement of the Version 1 breadboard with a custom printed circuit board.

The PCB was designed to integrate the electrical connections required by the Bluetooth audio system while reducing the amount of point-to-point wiring inside the enclosure.

The PCB design process included:

- Component placement
- Custom component footprints
- Power and signal routing
- Ground-plane implementation
- Trace-width selection
- Speaker-output routing
- Battery and power routing
- Via placement
- Design Rule Checking (DRC)
- PCB manufacturing preparation

The final PCB passed the configured design-rule checks before being submitted for manufacturing.

---

## PCB Layout

## PCB Layout

The custom PCB was designed in EasyEDA to integrate the PAM8403 stereo
audio amplifier, Bluetooth connections, power connections, and speaker outputs.

### PCB Design

<p align="center">
  <img src="PCB/Photos/PCB_3D_Top.png" width="500">
</p>

### Manufactured PCB

<p align="center">
  <img src="PCB/Photos/PCB_Manufactured_Top.jpeg" width="500">
</p>

The PCB uses wider traces for higher-current paths such as power and
speaker connections. Copper ground regions were incorporated to simplify
ground routing and provide a common ground reference.
---

## Power System

Version 2 replaces the four-AA battery system used in Version 1 with a rechargeable lithium-ion battery system.

The design uses an Adafruit PowerBoost 1000C to provide power management for the portable speaker.

This change is intended to eliminate two major limitations discovered during Version 1:

1. The batteries could not be recharged directly inside the speaker.
2. The Version 1 internal power module required manual activation before the external power switch could control the speaker.

The rechargeable system provides a more practical power architecture for a portable device.

---

## Audio System

The audio section receives stereo audio from the Bluetooth module and sends the left and right signals to the audio amplifier.

The amplifier then drives the left and right speakers using separate output channels.

The custom PCB provides the electrical connections between the Bluetooth receiver, amplifier circuitry, power system, and external speaker connections.

---

## Enclosure

Version 2 replaces the modified food container used in Version 1 with a dedicated plastic electronics enclosure.

The new enclosure is intended to provide:

- Improved component mounting
- Better protection for the electronics
- Cleaner external appearance
- More organized internal construction
- Improved portability
- More permanent mounting of switches, speakers, and electrical hardware

The PCB and other internal components will be installed after the manufactured board and remaining components are received and tested.

---

## Parts List

A complete Version 2 parts list will be maintained in the `Parts/` directory.

Major components include:

- Custom JF Audio PCB
- Bluetooth audio module
- Audio amplifier circuitry
- Two speakers
- Rechargeable lithium-ion battery
- Adafruit PowerBoost 1000C
- Plastic electronics enclosure
- External power switch
- PCB connectors
- Passive components
- Mounting hardware

---

## PCB Design Process

Version 2 provided experience moving from a prototype circuit to a manufacturable PCB.

Several design issues were identified and corrected during development, including:

- Component footprint configuration
- Schematic-to-PCB net consistency
- Net-name mismatches
- Unrouted connections
- Via routing
- Copper-region clearance
- Trace clearance
- Battery and speaker trace widths
- Design Rule Check errors

Resolving these issues was an important part of preparing the board for manufacturing.

---

## Manufacturing

The Version 2 PCB has been submitted for manufacturing.

Once the board is received, the next stages will include:

1. Visual inspection of the manufactured PCB
2. Continuity testing
3. Verification of power and ground connections
4. Component installation
5. Initial power testing
6. Bluetooth and audio testing
7. Speaker testing
8. Battery and charging testing
9. Installation into the enclosure
10. Final system testing

---

## Testing

Testing results will be documented after the Version 2 PCB and components are assembled.

Planned testing includes:

- PCB continuity testing
- Power-rail voltage measurements
- Ground continuity
- Bluetooth pairing
- Left/right audio-channel verification
- Speaker output testing
- Battery operation
- Charging operation
- Power-switch operation
- Extended playback testing

---

## Lessons From Version 1 Applied to Version 2

Version 1 demonstrated that the Bluetooth speaker architecture worked, but also identified several areas requiring improvement.

Version 2 directly addresses these findings through:

- Replacing breadboard wiring with PCB traces
- Reducing internal jumper wiring
- Improving component organization
- Adding rechargeable battery operation
- Improving power distribution
- Using a dedicated enclosure
- Creating a more permanent electrical assembly

The transition from Version 1 to Version 2 represents the progression from a functional proof-of-concept prototype toward a more integrated hardware design.

---

## Project Files

- [Photos/](Photos/) - Version 2 construction and assembly photographs
- [Parts/](Parts/) - Version 2 bill of materials and component information
- [PCB/](PCB/) - PCB design files, manufacturing files, and board images
- [Schematics/](Schematics/) - Electrical schematics and supporting design files

---

## Current Status

**In Development**

- [x] Version 1 prototype completed
- [x] Version 2 architecture developed
- [x] Custom PCB designed
- [x] PCB routing completed
- [x] Design Rule Check completed
- [x] PCB submitted for manufacturing
- [x] Components ordered
- [ ] PCB received
- [ ] PCB inspected and electrically tested
- [ ] Components assembled
- [ ] Initial power-up completed
- [ ] Bluetooth audio tested
- [ ] Rechargeable power system tested
- [ ] Enclosure assembled
- [ ] Final Version 2 testing completed

---

## Next Steps

The next stage of Version 2 will begin when the manufactured PCB and remaining components arrive.

The board will first be inspected and electrically tested before components are installed. After assembly, the power system will be tested before connecting the Bluetooth and audio sections.

Successful completion of Version 2 will provide the foundation for **JF Audio Version 3**, which will explore additional improvements in audio performance, hardware integration, enclosure design, power management, and user features.
