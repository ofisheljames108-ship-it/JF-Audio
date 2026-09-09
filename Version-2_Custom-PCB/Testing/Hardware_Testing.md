# JF Audio Version 2 - Hardware Testing

## Overview

This document records the hardware bring-up, electrical testing, audio verification, and troubleshooting performed on the JF Audio Version 2 system.

Testing was performed incrementally to verify each subsystem before final enclosure assembly.

The primary systems evaluated include:

- Custom JF Audio PCB
- PAM8403 stereo audio amplifier
- Bluetooth audio receiver
- Adafruit PowerBoost 1000C
- 3.7 V 18650 lithium-ion battery system
- Left and right speakers
- Power and ground distribution

Testing is still in progress as the Version 2 hardware is assembled and refined.

---


## Initial Bench Setup

![Initial JF Audio V2 Bench Test](Photos/Initial_Bench_Test.jpeg)

The Version 2 electronics were tested outside of the final enclosure to allow
individual subsystems to be measured and verified before permanent installation.

This bench configuration included the custom JF Audio PCB, Bluetooth receiver,
PAM8403 amplifier, PowerBoost 1000C, 18650 battery system, and both speakers.

---

# PCB Inspection and Continuity Testing

Before applying power, the manufactured PCB was visually inspected and tested using a digital multimeter.

Continuity testing was performed across the major power, ground, audio, and speaker connections.

## Results

- [x] PCB visually inspected
- [x] Power connections checked
- [x] Ground connections checked
- [x] Major signal connections checked
- [x] Speaker-output connections checked
- [x] No obvious 5 V-to-GND short detected

The continuity tests confirmed that the major PCB connections were electrically connected as intended before initial power-up.

---

# Initial Power Testing

The initial Version 2 power system used an Adafruit PowerBoost 1000C to convert the single-cell lithium-ion battery voltage to the regulated supply used by the custom PCB.

A 470 µF electrolytic bulk capacitor was connected externally across the regulated 5 V and GND rails after a PCB footprint issue prevented the intended capacitor from being installed directly at its original PCB location.

## Initial Voltage Measurements

| Measurement | Result | Status |
|---|---:|---|
| PowerBoost output | ~5.1 V | PASS |
| PCB 5 V rail | ~5.1 V | PASS |
| Voltage across 470 µF capacitor | ~5.1 V | PASS |

These measurements confirmed that the PowerBoost initially supplied the expected regulated voltage and that the supply successfully reached the custom PCB.

---

# Bluetooth Receiver Testing

After the power system and PCB supply voltage were verified, the Bluetooth receiver was connected to the custom PCB.

The Bluetooth module powered successfully and was detected by a mobile device.

## Results

- [x] Bluetooth module powered successfully
- [x] Bluetooth module operated normally
- [x] Mobile device detected the Bluetooth receiver
- [x] Bluetooth pairing completed successfully

Successful pairing confirmed that the Bluetooth receiver was receiving power and operating correctly when connected through the Version 2 hardware.

---

# Audio Amplifier Testing

After successful Bluetooth pairing, the PAM8403 amplifier channels were tested individually.

Testing one speaker channel at a time reduced the number of variables during initial audio verification.

## Left Audio Channel

The left speaker was connected to the left amplifier output and Bluetooth audio was played through the system.

### Results

- [x] Left speaker connected
- [x] Bluetooth audio received
- [x] PAM8403 left amplifier channel produced audio
- [x] Left speaker operated successfully

**Result: PASS**

---

## Right Audio Channel

After verifying the left channel, the right speaker was connected and tested.

### Results

- [x] Right speaker connected
- [x] Bluetooth audio received
- [x] PAM8403 right amplifier channel produced audio
- [x] Right speaker operated successfully

**Result: PASS**

---

# Stereo Audio Verification

Both speakers were successfully connected to the custom PCB and operated through the PAM8403 stereo amplifier.

The verified audio path was:

Bluetooth Receiver

↓

JF Audio Version 2 PCB

↓

PAM8403 Stereo Amplifier

↓

Left and Right Speakers

## Results

- [x] Left audio channel operational
- [x] Right audio channel operational
- [x] Both speakers operational

**Stereo Audio Test: PASS**

This represented the first successful stereo audio operation of the manufactured JF Audio Version 2 PCB.

---


# PowerBoost Wiring

### Top Side

![PowerBoost Top-Side Wiring](Photos/PowerBoost_Wiring_Top.jpeg)

### Bottom Side

![PowerBoost Bottom-Side Wiring](Photos/PowerBoost_Wiring_Bottom.jpeg)

The PowerBoost 1000C was integrated into the Version 2 power system to provide
the regulated supply required by the custom PCB.

Initial testing measured approximately 5.1 V at the PowerBoost output, PCB
power input, and external 470 µF bulk capacitor.

---


## PowerBoost Troubleshooting

During initial Version 2 integration, abnormal PowerBoost behavior was
observed. The original module exhibited unreliable operation and abnormal
thermal behavior during testing.

Troubleshooting included voltage measurements, enable-pin testing, battery
connection checks, and isolation of the PowerBoost from other system
components.

The original PowerBoost was ultimately replaced.

### Resolution

A replacement PowerBoost 1000C was installed and subsequently operated
successfully with the protected battery system.

Later integrated-system testing verified:

- Stable battery-powered operation
- External power-switch operation
- Bluetooth connectivity
- Stereo audio playback
- Battery charging
- Simultaneous charging and playback

**Status: RESOLVED**

## Integrated System Test

After individual subsystem testing, the Version 2 electronics were connected as a complete system.

The integrated system included:

- Custom JF Audio PCB
- PAM8403 stereo audio amplifier
- Bluetooth audio receiver
- Adafruit PowerBoost 1000C
- 18650 lithium-ion battery
- 1S battery protection PCB
- External power switch
- Left and right speakers

The battery was connected through the protection PCB before supplying the PowerBoost. The protected battery output was then used to power the PowerBoost, which supplied the 5 V electronics rail.

The complete system successfully powered on using the external switch. The Bluetooth receiver entered pairing mode, successfully paired with an audio source, and stereo audio playback was confirmed through both speakers.

### Result

**PASS**

The Version 2 electrical system operated successfully as a complete battery-powered Bluetooth speaker.

## Initial Playback Test

Following successful system integration, the speaker was operated continuously for approximately 15 minutes.

During the test:

- Bluetooth pairing remained stable
- Music playback remained continuous
- Both speakers operated correctly
- The external power switch operated correctly
- No unexpected shutdowns occurred

The speaker was manually turned off using the external power switch after approximately 15 minutes.

### Result

**PASS**

## Extended Playback Test

An extended battery-powered playback test was performed to evaluate system stability and thermal behavior.

The speaker operated continuously for approximately 1 hour while playing music.

During the test:

- Bluetooth connection remained stable
- Both audio channels continued operating
- No unexpected resets or shutdowns occurred
- No components exhibited abnormal overheating
- The power system remained stable

At the end of the test, the battery voltage measured approximately **3.77 V**.

### Result

**PASS**

The system demonstrated stable operation during one hour of continuous battery-powered audio playback.

## Battery Charging Test

Charging operation was tested using the Adafruit PowerBoost 1000C charging system.

Before charging, the battery had previously measured approximately **3.77 V** following the extended playback test.

During an early charging measurement:

- Battery voltage disconnected from the charger: approximately **3.92 V**
- Battery voltage while connected to the charger: approximately **3.97 V**

Charging was continued toward full charge.

Near the end of the charging cycle, the battery voltage stabilized at approximately **4.17 V** for an extended period while the PowerBoost charging indicator remained active.

The PowerBoost later indicated completion of the charging cycle, and the battery measured approximately **4.18 V**.

The battery protection PCB and battery did not exhibit abnormal heating during charging.

The PowerBoost charging circuitry became warm during portions of the charging process, with temperature decreasing as the battery approached full charge.

### Result

**PASS**

The rechargeable power system successfully charged the battery from a partially discharged state to approximately 4.18 V.

## Simultaneous Charging and Playback Test

The speaker was tested while connected to external charging power to verify that audio playback could continue during battery charging.

During the test:

- The speaker remained powered
- Bluetooth remained connected
- Music playback continued successfully
- Both speakers operated normally
- The charging system remained functional

### Result

**PASS**

The Version 2 system successfully supported audio playback while connected to charging power.

## Enclosure and Mechanical Fit Testing

Following successful electrical testing, development progressed to enclosure integration.

The Version 2 enclosure has an approximate internal usable area of:

- Length: **143 mm**
- Width: **72 mm**

The two speakers were positioned side-by-side on the enclosure lid.

The circular acoustic opening of each speaker was measured at approximately **65 mm diameter**.

Paper templates were created to evaluate speaker opening placement before modifying the enclosure. The templates were positioned on the enclosure lid to verify:

- Speaker spacing
- Clearance from enclosure edges
- Clearance from enclosure screw posts
- Speaker mounting-hole accessibility
- Available material between the two speaker openings

The actual speaker frames were also compared against the templates to confirm that the circular openings remain within the metal speaker frames while preserving the four mounting locations.

### Status

**IN PROGRESS**

Final speaker-hole cutting, mounting-hole drilling, electronics placement, and enclosure assembly have not yet been completed.

## Enclosure Integration

Following successful electrical and bench testing, the Version 2 electronics
were installed into the final enclosure.

Mechanical integration included:

- Fabrication of two speaker openings
- Drilling of speaker mounting holes
- Mechanical mounting of both speakers
- Installation of the custom JF Audio PCB
- Installation of the PowerBoost 1000C
- Installation of the protected 18650 battery system
- Installation of the Bluetooth receiver
- Installation of the external power switch
- Routing of internal power, audio, and speaker wiring
- Fabrication of an external charging-port opening

Due to limited internal space, several electronic components were mounted
using double-sided adhesive rather than dedicated mechanical mounting
hardware.

### Mechanical Design Observation

The off-the-shelf enclosure required manual fabrication of the speaker,
switch, and charging-port openings. This resulted in less precise external
features than desired.

Final assembly also revealed that the charging-port opening does not provide
sufficient clearance for the molded housing of the Micro-USB charging cable.
The opening will be refined before Version 2 is considered complete.

This limitation directly informs Version 3, which will use a purpose-designed
3D-printed enclosure with accurately dimensioned component mounts and
external-interface openings.

**Status: ASSEMBLY COMPLETE — FINAL CHARGING-PORT REVISION PENDING**

### Mechanical Design Observations

Manual modification of the off-the-shelf enclosure resulted in less precise
speaker and port openings than desired.

This identified an important design improvement for future revisions:
Version 3 will investigate a custom 3D-printed enclosure with integrated
component mounting locations, accurately dimensioned speaker openings,
switch mounting, and charging-port access.

### Result

**ENCLOSURE INTEGRATION: COMPLETE**

## Post-Assembly Extended Playback Test

After installation of the electronics and speakers into the enclosure, the
completed Version 2 speaker underwent extended Bluetooth playback testing.

The assembled speaker operated continuously for approximately **2.5 hours**.

During the test:

- Bluetooth connectivity remained operational
- Stereo audio playback continued successfully
- Both speaker channels remained functional
- The battery-powered system remained operational
- No unexpected shutdowns occurred

### Result

**2.5-HOUR POST-ASSEMBLY PLAYBACK TEST: PASS**

Successful operation after enclosure installation confirmed that the
mechanical assembly did not prevent normal operation of the primary audio
and power systems.

## Observed Behavior

The following observations were recorded:

- Battery voltage measured approximately 3.8 V
- PowerBoost boosted output measured approximately 0 V
- Red LOW indicator remained illuminated
- Abnormal heating was observed around the boost-converter IC
- No obvious 0-ohm short was measured across the primary power rails

Because the PowerBoost exhibited abnormal heating, additional battery-powered testing of the module was discontinued.

The exact cause of the failure has not been conclusively determined.

A replacement PowerBoost 1000C will be installed before additional system-level testing is performed.

---

# Battery Protection Improvement

During hardware bring-up, the selected 3.7 V 18650 lithium-ion cell was identified as an unprotected cell.

Because the battery does not contain an integrated protection circuit, a separate 1S lithium-ion battery protection module was added to the planned Version 2 power architecture.

The revised power architecture is:

18650 Battery

↓

1S Battery Protection Module

↓

PowerBoost 1000C

↓

JF Audio Version 2 PCB

The protection module will be installed and verified before final assembly.

This design change was made to improve battery protection and overall power-system robustness.

---

## Replacement PowerBoost Testing

Following installation of the replacement PowerBoost 1000C, the power,
audio, and control systems were retested to verify proper operation.

### Power System

- [x] Verify battery voltage
- [x] Verify protected battery output
- [x] Verify PowerBoost input voltage
- [x] Verify PowerBoost regulated output
- [x] Verify PCB supply voltage
- [x] Verify voltage across 470 µF bulk capacitor
- [x] Check for abnormal component heating

### Functional Retesting

- [x] Verify Bluetooth module power
- [x] Verify Bluetooth pairing
- [x] Re-test left audio channel
- [x] Re-test right audio channel
- [x] Verify stereo audio operation

### Power Control

- [x] Connect SPST rocker switch to PowerBoost enable control
- [x] Verify ON state
- [x] Verify OFF state
- [x] Confirm correct switch orientation

### Result

The replacement PowerBoost restored normal system operation. The protected
battery system, regulated power output, Bluetooth receiver, stereo audio
channels, and external power control were successfully verified.

Subsequent integrated-system testing also demonstrated battery-powered
playback, battery charging, simultaneous charging and playback, and extended
playback operation.

**REPLACEMENT POWERBOOST TESTING: PASS**

---

## Final System Testing

Following installation and verification of the replacement PowerBoost 1000C,
the integrated Version 2 system underwent additional functional and endurance
testing.

Completed testing includes:

- [x] Battery charging test
- [x] Extended playback test
- [x] Amplifier temperature check
- [x] Power-system temperature check
- [x] Enclosure installation
- [x] Final assembled-system power test
- [x] Final Bluetooth test
- [x] 2.5-hour post-assembly stereo playback test
- [x] Simultaneous charging and playback test

Remaining final validation:

- [ ] Refine charging-port opening for proper Micro-USB cable clearance
- [ ] Verify battery charging through the completed enclosure
- [ ] Verify simultaneous charging and playback through the completed enclosure
- [ ] Final wiring and mechanical inspection
- [ ] Final audio noise evaluation
- [ ] Final audio distortion evaluation

Version 2 will be considered complete after the remaining enclosure-level
charging and final inspection tests are successfully completed.

---

## Testing Summary

Version 2 hardware testing successfully demonstrated operation of the custom
JF Audio PCB and the complete Bluetooth stereo audio system.

Initial PCB bring-up verified:

- PCB continuity
- Approximately 5.1 V regulated power delivery
- Bluetooth receiver operation and pairing
- PAM8403 left-channel operation
- PAM8403 right-channel operation
- Stereo speaker operation

During early system integration, abnormal heating and operation of the original
PowerBoost 1000C were observed. The module was removed from service and
replaced. A dedicated 1S lithium-ion protection module was also incorporated
into the battery architecture.

Following installation of the replacement PowerBoost, the power system,
Bluetooth receiver, amplifier, speakers, and external power control were
successfully retested.

Subsequent system testing demonstrated:

- Protected battery-powered operation
- Stable Bluetooth pairing and stereo playback
- External power-switch operation
- Battery charging
- Simultaneous charging and playback
- Extended bench playback
- Complete enclosure integration
- Approximately 2.5 hours of continuous post-assembly playback

The final enclosure revealed a mechanical clearance issue around the Micro-USB
charging port. The charging-port opening must be refined to allow the charging
cable to fully seat before final enclosure-level charging validation can be
completed.

**Current Status: FINAL INTEGRATION AND VALIDATION**

Remaining work consists of correcting the charging-port clearance, verifying
charging and simultaneous charging/playback through the completed enclosure,
performing final audio evaluation, and completing the final electrical and
mechanical inspection.
