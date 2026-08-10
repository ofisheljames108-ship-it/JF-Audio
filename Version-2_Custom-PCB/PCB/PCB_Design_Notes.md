# JF Audio Version 2 - PCB Design Notes

## Overview

The JF Audio Version 2 PCB was designed to replace the breadboard-based wiring used in Version 1 with a more compact, organized, and permanent electrical system.

Version 1 successfully demonstrated the operation of the Bluetooth speaker, but the use of a breadboard, jumper wires, and separate modules required a significant amount of enclosure space and resulted in a large number of point-to-point connections.

Version 2 moves these connections onto a custom printed circuit board while also integrating the audio amplifier circuitry directly onto the PCB.

The PCB was designed and routed using EasyEDA and was submitted for fabrication after completing Design Rule Checking (DRC).

---

## Design Objectives

The primary objectives of the PCB were:

- Replace breadboard wiring with PCB traces
- Reduce the amount of point-to-point wiring
- Integrate the audio amplifier circuitry directly onto the PCB
- Provide dedicated connections for the Bluetooth module
- Provide dedicated left and right speaker connections
- Provide connections for the rechargeable power system
- Improve power and ground distribution
- Use wider traces for higher-current paths
- Maintain clear separation and organization of the audio and power sections
- Create a PCB that could be mounted inside a dedicated enclosure
- Gain experience with schematic capture, footprint creation, PCB routing, vias, copper regions, and DRC

---

## PCB Layout

### Top Layer

![JF Audio V2 PCB Top Layout](Images/PCB_2D_Top.png)

The top layer contains the primary component footprints and a significant portion of the signal and power routing.

Component placement was selected to keep related components close together and reduce unnecessary trace lengths.

Particular attention was given to the placement of the passive components surrounding the audio amplifier IC.

---

## 3D PCB Model

![JF Audio V2 PCB 3D Top](Images/PCB_3D_Top.png)

The EasyEDA 3D model was used to inspect the physical layout of the board before fabrication.

The 3D view helped verify:

- General component placement
- Connector locations
- Component spacing
- Mounting-hole locations
- Silkscreen placement
- Overall PCB proportions

---

## Audio Amplifier Section

Unlike Version 1, which used a complete PAM8403 amplifier module, Version 2 integrates the amplifier IC and its required supporting components directly onto the custom PCB.

The amplifier section includes the external passive components required for the audio and power connections.

Component placement around the amplifier was kept compact, particularly for components associated with power decoupling and the audio signal path.

This approach reduces dependence on a separate amplifier module and provides greater control over the physical PCB layout.

---

## Capacitor Placement

Capacitor placement was an important consideration during the PCB design.

Power-related capacitors were placed close to the amplifier IC and associated supply connections to reduce the length of the current paths between the capacitors and the device.

The smaller capacitors associated with the amplifier circuitry were also positioned close to their corresponding pins and resistors where practical.

A larger bulk capacitor is included on the power rail to help support the amplifier during changing load conditions.

---

## Audio Signal Routing

The PCB provides separate left and right audio paths between the Bluetooth receiver connections and the amplifier inputs.

The audio section was routed with the goal of keeping the signal paths organized and avoiding unnecessary routing through higher-current sections of the board.

The left and right amplifier outputs are routed to dedicated speaker connections.

---

## Speaker Outputs

The amplifier provides separate positive and negative outputs for each speaker channel.

The PCB therefore provides:

- Left Speaker +
- Left Speaker -
- Right Speaker +
- Right Speaker -

Each speaker is connected directly between the positive and negative outputs of its corresponding amplifier channel.

The negative speaker outputs are amplifier outputs and are not connected directly to ground.

Because the speaker outputs can carry more current than the small-signal audio connections, wider PCB traces were used for these paths.

---

## Power Routing

Version 2 uses a rechargeable power architecture rather than the four-AA battery system used in Version 1.

The PCB includes dedicated connections for the external power system and distributes the required supply voltage to the Bluetooth and amplifier circuitry.

Power traces were made wider than low-current signal traces where practical to reduce resistance and improve current handling.

Particular attention was given to the battery/power and amplifier-output paths because these connections are expected to carry more current than the audio-input signals.

---

## Grounding

Ground distribution was an important part of the PCB layout.

A copper ground region was used to provide a low-impedance common ground connection across the PCB and reduce the need for long individual ground traces.

The Bluetooth receiver, amplifier circuitry, power system, and supporting passive components ultimately share the system ground.

Grounding was also considered when routing the audio section because poor grounding can contribute to unwanted noise in an audio system.

---

## Via Usage

Vias were used where necessary to transition between PCB layers and complete connections that could not be routed cleanly on a single layer.

One routing challenge involved connecting nets around the amplifier IC while maintaining the correct electrical connections and required clearances.

Using vias allowed traces to transition between layers and continue routing without creating unintended connections or violating the PCB design rules.

---

## Trace Widths

Different trace widths were used depending on the expected function of each connection.

### Wider Traces

Wider traces were used for connections such as:

- Main power distribution
- Battery/power connections
- Amplifier power connections
- Left speaker output
- Right speaker output

### Signal Traces

Smaller traces were acceptable for lower-current connections such as:

- Left audio input
- Right audio input
- Control signals
- Other low-current connections

This approach allowed higher-current paths to use more copper while keeping the remaining PCB routing manageable.

---

## Component Footprints

Several component and footprint configurations required additional work during the design process.

Custom components and footprints were created in EasyEDA where necessary.

One issue encountered during development was EasyEDA reporting that a component lacked a footprint even though a footprint had been created.

This required verifying that the correct footprint was assigned to the corresponding schematic component rather than relying only on matching component and footprint names.

This provided useful experience with the relationship between schematic symbols, PCB footprints, and physical components.

---

## Net and Routing Troubleshooting

Several routing and net-related issues were encountered during PCB development.

One issue involved nets that appeared to have matching names but were still reported as electrically disconnected.

Troubleshooting included checking:

- Net assignments
- Net names
- Capitalization
- Pad assignments
- Trace connections
- Layer transitions
- Via connections
- Copper continuity

A via was ultimately used in one of the difficult routing areas to transition between PCB layers and create the required continuous electrical connection.

This demonstrated that matching net labels alone do not guarantee that a physical copper connection exists on the PCB.

---

## Design Rule Checking

Design Rule Checking was performed before the PCB was submitted for manufacturing.

The DRC process was used to identify problems including:

- Unconnected nets
- Routing conflicts
- Clearance violations
- Copper-region issues
- Via-related routing problems
- Other PCB rule violations

Each reported issue was investigated and corrected.

The final PCB design completed DRC with no remaining reported errors before manufacturing.

---

## Silkscreen and Board Identification

The PCB includes custom silkscreen markings to identify the project and board revision.

The bottom side includes:

- JF Audio branding
- Mark II identification
- CSUSM identification

![JF Audio V2 PCB Bottom](Images/PCB_3D_Bottom.png)

These markings distinguish the Version 2 PCB from the original prototype and provide visual identification of the project.

---

## Manufacturing Preparation

Before submitting the board for fabrication, the design was reviewed for:

- Component placement
- Trace routing
- Power connections
- Speaker connections
- Ground connectivity
- Via placement
- Footprint assignments
- Silkscreen placement
- Mounting holes
- Design Rule Check results

After the final review and successful DRC, the PCB was submitted for manufacturing.

---

## Planned Hardware Verification

Once the manufactured PCB is received, the board will be tested before full system operation.

Initial verification will include:

1. Visual inspection of the PCB
2. Inspection for manufacturing defects
3. Continuity testing of important nets
4. Checking for shorts between power and ground
5. Verification of amplifier connections
6. Verification of Bluetooth-module connections
7. Verification of speaker-output connections
8. Initial power testing
9. Audio testing
10. Rechargeable power-system testing

Results from these tests will be documented after assembly.

---

## Improvements Over Version 1

The Version 2 PCB addresses several limitations discovered during the original prototype.

| Version 1 | Version 2 |
|---|---|
| Breadboard | Custom PCB |
| PAM8403 amplifier module | Amplifier IC integrated onto PCB |
| Jumper-wire connections | PCB traces |
| Large wiring footprint | More compact routing |
| AA battery system | Rechargeable power system |
| No integrated charging | Rechargeable power architecture |
| Modified food container | Dedicated enclosure |
| Prototype construction | More permanent assembly |

---

## Current Status

- [x] PCB schematic/design completed
- [x] Component footprints configured
- [x] Component placement completed
- [x] PCB routing completed
- [x] Vias added where required
- [x] Ground copper implemented
- [x] Power and speaker trace widths reviewed
- [x] DRC errors resolved
- [x] PCB submitted for manufacturing
- [x] Components ordered
- [ ] Manufactured PCB received
- [ ] PCB continuity tested
- [ ] Components assembled
- [ ] Initial power-up completed
- [ ] Audio functionality tested
- [ ] Rechargeable power system tested
- [ ] Final enclosure assembly completed

---

## Summary

The JF Audio Version 2 PCB represents the transition from a breadboard-based proof of concept to a purpose-built hardware design.

The design process provided practical experience with component placement, PCB routing, trace sizing, grounding, vias, footprint management, design-rule checking, and preparing a custom PCB for manufacturing.

The next stage of the project will focus on validating the manufactured PCB, assembling the components, testing the electrical system, and integrating the completed hardware into the Version 2 enclosure.
