# JF Audio Version 1 - Prototype

![JF Audio Version 1 Finished Speaker](Photos/v1_finished_speaker.jpg)

## Overview

Version 1 of JF Audio was the first working prototype of my portable Bluetooth speaker project. The goal of this version was to build a functional portable Bluetooth speaker using off-the-shelf modules and readily available materials before moving toward a custom PCB design.

The electronics were assembled primarily using a breadboard and jumper wires and were housed inside a modified American Maid 1.06 L food container. Two 8-ohm, 1-watt speakers were mounted to the lid of the enclosure.

This version served as a proof of concept and provided experience with Bluetooth audio, audio amplification, power distribution, grounding, soldering, troubleshooting, and physical assembly.

---

## Design Goals

- Build a functional portable Bluetooth speaker
- Implement wireless stereo audio using a Bluetooth receiver
- Learn how a Bluetooth audio module interfaces with an audio amplifier
- Develop experience with power distribution and grounding
- Practice soldering and hardware assembly
- Create a portable enclosure for the electronics
- Identify electrical and mechanical limitations of the prototype
- Use the completed prototype as the foundation for a custom PCB design

---

## Features

- Wireless Bluetooth audio playback
- Two-channel stereo audio
- HiLetgo M18 Bluetooth audio module
- HiLetgo PAM8403 stereo audio amplifier
- Two 8-ohm, 1-watt speakers
- Four-AA battery power source
- Regulated 5 V electronics supply
- External SPST rocker switch
- Breadboard-based construction
- Portable plastic enclosure

---

## System Architecture

Version 1 consists of four primary sections:

1. Battery and power supply
2. Bluetooth audio receiver
3. Stereo audio amplifier
4. Left and right speakers

Four AA batteries connected in series provide approximately 6 V nominal. A 5 V power supply module regulates this voltage to provide power for the Bluetooth receiver and audio amplifier.

The regulated 5 V supply passes through an external SPST rocker switch before powering the audio electronics.

The M18 Bluetooth module receives wireless stereo audio and provides left and right audio signals to the PAM8403 amplifier. The PAM8403 then amplifies these signals and drives the two speakers.

### Signal and Power Flow

`4x AA Batteries (6 V nominal) → 5 V Power Supply → SPST Switch → M18 Bluetooth Module → PAM8403 Amplifier → Speakers`

---

## Circuit Schematic

The electrical connections used in Version 1 were recreated in LTspice for documentation.

![JF Audio Version 1 Circuit Schematic](Schematics/JF_Audio_V1_Schematic.png)

The schematic shows the complete signal and power path from the battery pack through the power supply and audio system.

The four-AA battery pack provides approximately 6 V nominal to the power supply module. The module regulates the supply to 5 V, which is routed through the SPST rocker switch before powering the M18 Bluetooth module and PAM8403 amplifier.

The left and right audio outputs of the M18 are connected to the corresponding inputs of the PAM8403.

Each 8-ohm speaker is connected between the positive and negative output terminals of its respective PAM8403 channel.

The original LTspice `.asc` schematic and custom `.asy` symbols are included in the `Schematics` directory.

---

## Internal Electronics

![JF Audio V1 Internal Layout](Photos/v1_internal_layout.jpg)

Version 1 used a breadboard-based design with individual modules connected using jumper wires and soldered connections.

This approach provided flexibility during development because connections could easily be changed while troubleshooting the circuit.

However, the breadboard, individual modules, and large number of wires required significant space inside the enclosure. This became one of the primary motivations for designing a custom PCB for Version 2.

---

## Breadboard Wiring

![JF Audio V1 Breadboard Wiring](Photos/v1_breadboard_wiring.jpg)

The Bluetooth receiver, audio amplifier, and power circuitry were interconnected using a breadboard, jumper wires, and soldered wiring.

The breadboard approach made it possible to build and test the system before committing to a permanent circuit design.

This prototype also helped determine which electrical connections would later need to be incorporated into the custom PCB.

---

## Module Connections

![JF Audio V1 Module Connections](Photos/v1_module_connections.jpg)

The M18 Bluetooth receiver provides the left and right audio signals used by the PAM8403 amplifier.

The PAM8403 amplifies these signals and drives the two 8-ohm speakers using separate left and right amplifier channels.

The Bluetooth receiver and amplifier share the regulated 5 V power supply and common ground system.

---

## Power System

![JF Audio V1 Power Switch](Photos/v1_power_switch.jpg)

Version 1 is powered by four AA batteries connected in series, providing approximately 6 V nominal.

The battery pack connects to a 5 V power supply module, which provides regulated 5 V power for the Bluetooth receiver and audio amplifier.

An external SPST rocker switch controls the regulated power supplied to the audio electronics.

However, the power supply module itself contains an onboard push button that must first be activated before power reaches the external rocker switch. This means that the enclosure may need to be opened to access the internal power-module button.

Version 1 does **not** contain an integrated rechargeable battery system.

A rechargeable system using an Adafruit PowerBoost 1000C was considered for the original design but could not be implemented with the materials available during the Version 1 build.

The limitations of this power system became an important design consideration for Version 2.

---

## Parts List

A complete list of the primary components and materials used in Version 1 is available here:

[View the Version 1 Parts List](Parts/Parts_List.md)

Major components include:

- HiLetgo M18 Bluetooth audio module
- HiLetgo PAM8403 stereo audio amplifier
- Two 8-ohm, 1-watt speakers
- Four Amazon Basics AA batteries
- Four-cell AA battery holder
- 5 V power supply module
- SPST rocker switch
- Breadboard
- Jumper and hookup wires
- 3M double-sided tape
- American Maid 1.06 L food container

---

## Results

Version 1 successfully demonstrated a functional portable Bluetooth speaker.

The completed prototype was able to:

- Receive audio wirelessly over Bluetooth
- Produce stereo audio through two speakers
- Operate from a portable battery source
- Provide external power control
- Integrate the audio, power, and speaker hardware into a single portable enclosure

Most importantly, Version 1 validated the overall system architecture before development of a custom PCB.

---

## Lessons Learned

Version 1 revealed several areas that could be improved in future revisions.

- Breadboard construction requires significant enclosure space.
- Large numbers of jumper wires make assembly and troubleshooting more difficult.
- Proper grounding and power distribution are important for reducing unwanted audio interference.
- Component placement and wire management significantly affect the organization of the finished system.
- A dedicated PCB can reduce wiring and provide more reliable electrical connections.
- A purpose-built enclosure can improve component mounting and overall appearance.
- The internal power module requires manual activation before the external switch can operate.
- The lack of integrated battery charging reduces the convenience of the portable design.
- Building a working prototype before designing a PCB helped identify electrical and mechanical requirements for the next revision.

These observations directly influenced the design of **JF Audio Version 2**.

---

## Version Progression

### Version 1 - Prototype

Breadboard-based electronics, off-the-shelf modules, hand wiring, AA battery power, two 8-ohm 1-watt speakers, and a modified food-container enclosure.

**Primary objective:** Build and validate a functional portable Bluetooth speaker.

↓

### Version 2 - Custom PCB

Custom PCB design, dedicated plastic enclosure, improved component organization, reduced wiring, and an Adafruit PowerBoost 1000C for rechargeable battery operation.

**Primary objective:** Transform the working prototype into a cleaner, more integrated, and rechargeable design.

↓

### Version 3 - Future Development

Future improvements are currently being explored. Potential areas of development include improved audio performance, greater hardware integration, enhanced power management, custom enclosure design, and additional user features.

---

## Project Files

- [Photos/](Photos/) - Photographs of the completed prototype and internal construction
- [Parts/](Parts/) - Version 1 component and material list
- [Schematics/](Schematics/) - LTspice schematic and schematic image
- [Schematics/Symbols/](Schematics/Symbols/) - Custom LTspice symbols created for the project
---

## Status

**Complete**
