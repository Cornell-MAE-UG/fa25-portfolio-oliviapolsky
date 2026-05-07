---
layout: project
title: "No Fly Zone — SLF Trap"
description: "A spotted lanternfly lure and trap for vineyards, developed for Cornell CALS Extension, E&J Gallo Winery, and National Grape."
technologies: [3D Printing, Arduino, CAD]
image: /assets/images/ODP.png
Team: No Fly Zone
Client(s): Cornell CALS Extension / E&J Gallo Winery / National Grape
---
## Table of Contents
[Client Pitch](#client-pitch)
[Functional Prototype](#functional-prototype)
[Final Report](#final-report)

## Client Pitch

### Problem Statement
The spotted lanternfly (Lycorma delicatula, SLF) is an invasive species spreading prolifically throughout North America. SLFs feed on grapevines, depleting nutrients and reducing crop yield, and they remain on vines during harvest, contaminating the grapes. Economic losses to the grape industry in the Finger Lakes AVA alone are estimated to reach $1.5 million in the first year of infestation, with damages projected to double annually. Grapevines under heavy infestation have been shown to use 38% less water due to reduced sap flow, reflecting significant physiological stress. Current management options are difficult to deploy at scale across large vineyards during the growing season.

### Why It Matters
Reducing SLF population density before harvest would improve both yield and grape quality. It would also reduce SLF repopulation across seasons, protecting the long-term viability of the vineyard. Adult SLFs are the primary threat: they consume the most plant sap and produce honeydew that promotes sooty mold growth, further reducing photosynthetic capacity and affecting grape appearance.

### Proposed Direction: "The Lure"
A device hung from a trellis uses a dual-attraction system — a wintergreen-oil-soaked sponge surrounding a 60 Hz speaker — to draw SLFs in. Once inside, a motor-driven rotating trap disk guides them down into a removable screw-in capture chamber. The device is powered by an onboard solar cell.
Minimum viable product: A plastic housing with a wintergreen oil lure and a one-way valve entrance (resembling a heart valve) that allows SLFs to enter but not exit.
Long-term product: Full dual-lure system with rotating trap disk, quarantine tubes, replaceable capture chamber, and solar power.

### Key Risks

Efficacy: SLF attraction to the lure cannot be easily tested in a classroom setting; field testing will be required.
Cost: Deploying one device per vine across a large vineyard could be prohibitively expensive.
Maintenance: Manual servicing of each trap (emptying chamber, replacing components) requires significant labor at scale.

### Questions for the Client

What financial investment would be available for full-scale deployment? (Informs how many units are feasible and what per-unit cost target we should design toward.)
How much labor is realistically available for ongoing maintenance? (Informs how often the capture chamber needs to be serviceable and whether automation of any maintenance step is worth pursuing.)

References:

Source 1 — JIPM: SLF economic impact
Source 2 — Sci. Dir.: Grapevine sap flow study
Source 3 — JEE: SLF management


## Functional Prototype

No Fly Zone's first functional prototype is a SLF lure and trap that uses wintergreen oil as an attractant and a motor-driven rotating disk mechanism to guide insects into a removable capture chamber. The prototype was 3D printed and assembled with an Arduino-controlled DC motor, slide switch, battery pack, and screw-in storage container.

### Design Overview
The trap consists of a weather-shielding top cap, an outer housing with SLF entryways, an internal rotating disk (rotor + stator) driven by a DC motor via a drive shaft, quarantine tubes that channel insects away from the motor, and a screw-in capture chamber at the base. A wintergreen-oil-soaked sponge sits in the lower housing to attract insects. An Arduino controls the motor, toggled by a slide switch; an LED indicates that the motor is running.

Total BOM cost: $58.80
Key components include: 3D-printed housing, rotor disc, stator disc, rotors, stators, quarantine tubes, and top shade (RPL-fabricated); drive shaft (McMaster #89845K71, $1.15); DC motor (1.5–5V); Arduino processor; NPN transistor; 6V battery pack; breadboard; wintergreen oil ($7.99); sponge ($2.99); slide switch; green LED; and wiring.

### Assembly Instructions

1. Glue the two top shade pieces together.
2. Assemble the circuit according to the wiring diagram (Arduino → NPN transistor → DC motor, powered by 6V battery pack, with slide switch and LED).
3. Insert the small stator pieces into the stator disc. Slide the stator and its spacing ring onto the drive shaft.
4. Press-fit the drive shaft into the rotor piece.
5. Solder the drive shaft to the motor shaft, then seat the motor in its housing.
6. Slide the motor + stator + rotor + spacer ring assembly into the main housing. Insert the circuitry, battery pack, wintergreen oil sponge, and large spacer ring into the         lower housing beneath the mechanism.
7. Fit the storage container lid into the bottom of the housing, aligning the quarantine tubes with the holes.
8. Screw the storage container onto the bottom of the housing.
9. Set the top shade into position and attach hanging string to the top.

### Design Tests
Test 1 — Degree of rotation (motion & interference)

Testing: Motor was powered on and the rotor was also spun by hand to check for part alignment and interference through a full 360° range of motion.
Result: No interference; full 360° rotation confirmed. However, the shaft-to-motor connection (taped) displaced component seating, preventing the assembly from sliding down fully.
Conclusion: Replace tape connection with adhesive glue for the next iteration to ensure proper component seating.

Test 2 — Minimum motor voltage (with rotor attached)

Testing: Rotor attached to motor; voltage swept upward to find minimum for continuous motion and for startup.
Result: Continuous motion requires 1.74 V; startup requires 2.47 V.
Conclusion: Current 6V battery setup provides sufficient headroom. Arduino PWM output will be tuned accordingly.

Test 3 — Minimum rotating speed

Testing: Minimum sustained motor speed measured with shaft and rotor attached under battery power.
Result: Minimum sustained speed is 45 RPM.
Conclusion: 45 RPM may be too fast to gently guide insects rather than fling them. A stepper motor will be evaluated for the next iteration to allow slow, controlled rotation.

### Success Criteria
No Fly Zone is designing a SLF lure that attracts insects via wintergreen oil and captures them using a rotating trap disk that guides them into a lower storage chamber, powered continuously by a motor.
#CriterionMeasurementPriority1Hangable on a grapevine trellis; mass ≤ 1 kgWeigh assembled unit on a scaleMinimize mass2Packed volume ≤ 1 LMeasure outer dimensions, calculate volumeMinimize volume3User can turn on/off with a single mechanism in ≤ 5 secondsTime 5 testers operating the switch without instructionNot a priority to improve beyond threshold4Operates continuously for ≥ 24 hours under solar powerRun unit on solar input, log runtime until failureMaximize runtime
Exhibit demo: Criterion 3 (the on/off switch) will be demonstrated live. A tester will be handed the assembled trap and asked to turn it on without instruction; success or failure is immediately observable and ties directly to the usability criterion.

## Final Report

### Context and Problem Statement

The spotted lanternfly (*Lycorma delicatula*, SLF) is an invasive species spreading prolifically throughout North America. SLFs remain on grapevines during the harvesting process, contaminating the grapes and further decreasing yields. There is currently no efficient, non-damaging, low-labor method to remove SLFs from vines. This product aims to reduce SLF population density at the vine level without causing physical damage to grapevines, while minimizing labor requirements.

### Final Prototype

Our team designed a trellis-mounted device that attracts and removes SLFs using a combination of sensory lures and motorized capture. The device operates in two stages: attraction and capture. Wintergreen oil placed at the device opening lures SLFs inside, where the enclosure geometry guides them into a second chamber. A geared DC motor drives a rotating, toothed mechanism that physically directs SLFs into an isolated, removable collection chamber. The system is externally mounted and avoids direct contact with grapevines.

### Testing and Results

Three tests were conducted to validate the design against success criteria:

**Test 1 — Degree of rotation:** Full 360° rotation confirmed with no part interference. The shaft-to-motor tape connection was identified as a source of misalignment and will be replaced with adhesive in future iterations.

**Test 2 — Minimum motor voltage:** Continuous rotation requires 1.74 V; startup requires 2.47 V. Both are within the 6V battery pack's capability.

**Test 3 — Minimum rotating speed:** Minimum sustained speed was 45 RPM, which was deemed too fast and potentially startling to insects. The motor was swapped for one operating at 20 RPM with lower power draw, enabling smoother and more controlled operation.

The 4×AA battery pack, based on current calculations, can sustain operation for approximately six days — well beyond the 24-hour success criterion.

### Conclusion and Recommendations

The prototype met all three success criteria: mass and volume within targets, single-switch operation, and 24+ hour runtime. Key recommendations for scaling:

- **Control panel:** An Arduino-based network panel could monitor battery and functionality across multiple deployed units, reducing servicing labor by targeting only devices that need attention.
- **Solar power:** Rechargeable batteries powered by solar panels would eliminate the need to manually replace batteries across a large vineyard.
- **Acoustic lure:** Replacing wintergreen oil with a 60 Hz speaker (a frequency shown to attract SLFs) would eliminate the maintenance cost of re-oiling every few days.
- **Size reduction:** Redesigning the housing geometry and repositioning the motor could reduce weight, material usage, and production cost, making large-scale deployment more practical.

Field testing with actual SLFs in a controlled environment is the recommended next step to quantify attraction efficacy and strengthen any future client pitch.

**Total BOM Cost: $155.79**


