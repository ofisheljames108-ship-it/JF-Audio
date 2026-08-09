# JF Audio Version 1 - Parts List

This document lists the primary components and materials used to construct the first JF Audio Bluetooth speaker prototype.

| Component | Quantity | Purpose |
|---|---:|---|
| HiLetgo M18 Bluetooth Audio Module | 1 | Receives wireless Bluetooth audio from the source device |
| HiLetgo PAM8403 Audio Amplifier Module | 1 | Amplifies the left and right audio signals to drive the speakers |
| 8 Ω, 1 W Speaker | 2 | Left and right audio output |
| 5 V Power Supply Module | 1 | Provides regulated power to the speaker electronics |
| 4-Cell AA Battery Holder | 1 | Holds the batteries used to power the system |
| Amazon Basics AA Battery | 4 | Portable power source |
| SPST Rocker Switch | 1 | Provides external ON/OFF power control after activation of the internal power module |
| Breadboard | 1 | Provides a platform for prototype circuit connections |
| Jumper Wires / Hookup Wire | Various | Connects the power, Bluetooth, amplifier, and speaker circuitry |
| 3M Double-Sided Tape | As needed | Secures components inside the enclosure |
| American Maid 1.06 L Food Container | 1 | Prototype speaker enclosure |

## Power System Note

Version 1 does not contain an integrated rechargeable battery system. Four AA batteries provide the portable power source through a 5 V power supply module.

The power supply module requires activation using its onboard push button before power reaches the external SPST rocker switch. This limitation was identified during testing and influenced the power-system redesign planned for JF Audio Version 2.

## Version 1 Design Approach

Version 1 was intentionally constructed using readily available modules, a breadboard, and hand wiring. The purpose of this revision was to demonstrate a functional Bluetooth speaker before investing in a dedicated PCB and more integrated power system.

The experience gained from this prototype directly influenced the component selection, PCB design, power management, and enclosure improvements introduced in Version 2.
