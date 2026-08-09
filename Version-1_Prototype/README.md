# JF Audio Version 1 - Prototype

![JF Audio Version 1 Finished Speaker](Photos/v1_finished_speaker.jpg)

## Overview

Version 1 of JF Audio was the first working prototype of my portable Bluetooth speaker project. The goal of this version was to build a functional Bluetooth speaker using off-the-shelf modules and readily available materials before moving toward a custom PCB design.

The electronics were assembled primarily using a breadboard and jumper wires and were housed inside a modified plastic food container. Two 8-ohm, 1-watt speakers were mounted to the lid of the enclosure.

This prototype served as a proof of concept and provided experience with Bluetooth audio, audio amplification, battery-powered electronics, soldering, power distribution, and physical assembly.

---

## Design Goals

- Build a functional portable Bluetooth speaker
- Learn how Bluetooth audio modules and audio amplifiers interface
- Develop experience with power distribution and grounding
- Practice soldering and hardware assembly
- Create a portable enclosure for the electronics
- Identify limitations that could be improved in future revisions
- Use the prototype as a foundation for a future custom PCB design

---

## Features

- Wireless Bluetooth audio playback
- Two-channel stereo audio
- Two 8-ohm, 1-watt speakers
- Rechargeable battery-powered operation
- External rocker power switch
- Breadboard-based electronics
- Modified food-container enclosure

---

## Internal Electronics

![JF Audio V1 Internal Layout](Photos/v1_internal_layout.jpg)

Version 1 used a breadboard-based design with individual modules connected using jumper wires. This approach allowed the circuit to be modified and troubleshot easily during development.

Although this worked well for prototyping, the large number of individual wires and separate modules increased the amount of space required inside the enclosure. This became one of the primary motivations for developing a custom PCB in Version 2.

---

## Breadboard Wiring

![JF Audio V1 Breadboard Wiring](Photos/v1_breadboard_wiring.jpg)

The amplifier, Bluetooth receiver, and power circuitry were interconnected using a combination of breadboard connections, jumper wires, and soldered wiring.

The breadboard approach provided flexibility during initial testing and made it possible to verify the operation of individual sections of the speaker before creating a more permanent design.

---

## Module Connections

![JF Audio V1 Module Connections](Photos/v1_module_connections.jpg)

Individual modules were connected using jumper wires and soldered connections. This allowed the Bluetooth receiver, audio amplifier, speakers, and power system to operate as a complete system while still allowing components to be disconnected or modified during troubleshooting.

---

## Power Control

![JF Audio V1 Power Switch](Photos/v1_power_switch.jpg)

An external rocker switch provides the primary user-accessible power control. However, the internal battery power module must first be activated using its onboard push button before power reaches the external switch.

Once the internal power module is activated, the external rocker switch can control power to the speaker electronics.

This arrangement worked for the prototype but introduced an inconvenience because the enclosure must be opened whenever the battery module requires manual activation.

---

## Lessons Learned

Version 1 successfully demonstrated that the overall Bluetooth speaker concept could work, while also revealing several areas for improvement.

- Breadboard and jumper-wire construction requires significant enclosure space.
- Large amounts of wiring make assembly and troubleshooting more difficult.
- Proper grounding and power distribution are important for minimizing unwanted audio noise.
- Component placement and wire management have a significant effect on the organization of the final assembly.
- A dedicated PCB can significantly reduce wiring and improve reliability.
- A purpose-built enclosure can provide better component mounting and a cleaner finished product.
- The power system required access to an internal push button before the external power switch could operate, motivating a more integrated and accessible power-control design for future revisions.
- Building a functional prototype before designing a PCB helped identify electrical and mechanical improvements for the next version.

These observations directly influenced the development of **JF Audio Version 2**, which transitions from a breadboard-based prototype to a custom-designed PCB and a dedicated plastic enclosure.

---

## Version Progression

**Version 1 - Prototype**

Breadboard-based electronics, off-the-shelf modules, hand wiring, and a modified food-container enclosure.

↓

**Version 2 - Custom PCB**

Custom PCB design, improved component organization, reduced wiring, and a dedicated plastic enclosure.

↓

**Version 3 - Future Development**

Planned improvements will focus on further integration, improved audio performance, power management, enclosure design, and additional user features.

---

## Status

**Complete**
