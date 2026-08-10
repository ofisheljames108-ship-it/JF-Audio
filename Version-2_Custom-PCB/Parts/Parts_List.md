# JF Audio Version 2 - Parts List

This document lists the primary electrical, mechanical, and PCB-level components used in JF Audio Version 2 (MRK II).

Version 2 replaces the breadboard-based construction and AA battery system used in Version 1 with a custom PCB, rechargeable lithium-ion battery system, and dedicated plastic enclosure.

---

## Major Components

| Component | Part / Model | Quantity | Purpose |
|---|---|---:|---|
| Custom PCB | JF Audio MRK II | 1 | Main PCB for amplifier, power, Bluetooth, and speaker interconnections |
| Power / Charging Module | Adafruit PowerBoost 1000C | 1 | Provides rechargeable battery charging and regulated 5 V output |
| Audio Amplifier IC | PAM8403 | 1 | Stereo Class-D audio amplification |
| Bluetooth Module | HiLetgo M18 Bluetooth Audio Module | 1 | Receives wireless Bluetooth audio |
| Speakers | 8 Ω, 3 W | 2 | Left and right audio output |
| Battery | 3.7 V, 2.6 Ah 18650 Li-ion Cell | 1 | Rechargeable portable power source |
| Battery Holder | Single-cell 18650 holder with wire leads | 1 | Holds and connects the 18650 battery |
| Power Switch | SPST Rocker Switch | 1 | External power control |
| Enclosure | Plastic electronics enclosure | 1 | Houses the PCB, battery, speakers, and supporting electronics |

---

## PCB Components

### Resistors

| Reference | Component | Value | Part Number | Quantity | Purpose |
|---|---|---:|---|---:|---|
| R1, R2 | SMD Resistor | 20 kΩ | 0603WAF2002T5E | 2 | Left and right amplifier input resistors |

---

### Capacitors

| Reference | Component | Value | Part Number / Type | Quantity | Purpose |
|---|---|---:|---|---:|---|
| C4, C5 | Ceramic Capacitor | 0.47 µF | CL10B474KA8NNNC | 2 | Left and right audio-input coupling capacitors |
| C6, C7, C8 | Ceramic Capacitor | 1 µF | CL10A105KB8NNNC | 3 | Local amplifier power-supply decoupling |
| C9 | Ceramic Capacitor | 0.1 µF | CC0603KRX7R9BB104 | 1 | VREF bypass capacitor |
| C10 | Bulk Capacitor | 470 µF | Polarized capacitor | 1 | Bulk PVDD power-supply decoupling |

---

## C10 Design Note

The PAM8403 typical application circuit specifies a 470 µF bulk capacitor between the PVDD supply rail and ground.

C10 was therefore intentionally specified as **470 µF** in the JF Audio MRK II schematic.

However, the first PCB revision accidentally assigned C10 a **C0603 footprint**, which is far too small for a typical 470 µF capacitor.

As a result, C10 was not included in the PCB assembly order and is expected to require manual installation or an alternate connection to the 5 V and ground rails.

This footprint issue will be corrected in a future PCB revision.

---

## PAM8403 Supporting Circuit

The amplifier section follows the general supporting-component arrangement shown in the PAM8403 reference design.

The main external components include:

- 0.47 µF audio-input coupling capacitors
- 20 kΩ input resistors
- 1 µF power-supply decoupling capacitors
- 0.1 µF VREF bypass capacitor
- 470 µF bulk power-supply capacitor

The PAM8403 provides separate bridge-tied left and right speaker outputs, allowing each speaker to connect directly between the positive and negative terminals of its corresponding amplifier channel.

---

## Power System

Version 2 uses a single rechargeable 3.7 V 18650 lithium-ion battery.

The Adafruit PowerBoost 1000C provides the rechargeable power architecture and regulated 5 V supply used by the speaker electronics.

This replaces the four-AA battery system used in Version 1.

---

## Additional Materials

| Material | Quantity | Purpose |
|---|---:|---|
| Hookup Wire | As needed | Connections between PCB and off-board hardware |
| Double-Sided Mounting Tape | As needed | Securing modules/components inside enclosure |
| PCB Mounting Hardware | As needed | Mounting PCB inside enclosure |
| Solder | As needed | Electrical assembly |

---

## PCB Assembly Notes

The following components were included in the PCB assembly configuration:

- PAM8403 amplifier IC
- R1 and R2
- C4 and C5
- C6, C7, and C8
- C9

C10 was not included in the assembly due to the incorrect footprint assignment and will be addressed separately during hardware assembly.

---

## Revision Note

**JF Audio MRK II - PCB Revision 1**

Known issue:

- C10 is correctly specified electrically as 470 µF, but the PCB footprint was incorrectly assigned as C0603.

Planned correction for a future PCB revision:

- Replace the C0603 footprint with an appropriately sized polarized electrolytic or polymer capacitor footprint.
