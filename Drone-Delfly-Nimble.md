# DelFly Nimble (aka Transformer)

- [Introduction](#introduction)
- [Paparazzi Code](#paparazzi-code)
- [Flight Procedure](#flight-procedure)
- [Scientific Papers and Thesis](#scientific-papers-and-thesis)
- [Extra information](#extra-information)

## Introduction
DelFly Nimble is our newest and most agile design which can hover or fly in any direction (up, down, forward, backward or sideways). Unlike its predecessors, which are controlled like a conventional airplane via deflections of control surfaces located on the tail or behind the wings, the DelFly Nimble has no tail nor such control surfaces. Instead, it is controlled through insect-inspired adjustments of motion of its two pairs of flapping wings. The lack of the tail makes the DelFly Nimble less vulnerable to damage and highly agile, allowing also outdoors operation in light winds.

![Transformer](https://github.com/tudelft/mavlab/raw/master/photos/drones/nimble/nimble_components.jpg)

(A) Description of the robot’s components. (B to D) High-speed camera frames capturing the robot in hover (B), forward flight (C), and sideways flight (D), from movies S1 to S3, respectively. (E to G) Details of the robot design: (E) the wing root adjustment mechanism for yaw torque control, (F) the dihedral control.

<a href="#top">[Back to top]</a>

## Paparazzi Code
**The latest code (limited functionality)** will be soon in Paparazzi master (based on this [PR](https://github.com/paparazzi/paparazzi/pull/2380), allows basic flying + Optitrack flying):
* [DelFly Nimble airframe file, PPRZ master](https://github.com/paparazzi/paparazzi/blob/master/conf/airframes/tudelft/delfly_nimble.xml)

**Every Nimble might be different**, e.g. motors might be connected to different pins than in the master airframe, so always check before flying!!
Also, after replacing the pitch servo, or if the Nimble starts drifting over time, you might want to adjust the dihedral servo limits in the airframe file to trim the vehicle.

If you need additional functionality (onboard logging, rpm sensing, range sensor, monocam), you need to start from older code. If you plan to do further development, these additional features should be reintegrated into the latest code.

**Old, but flight tested code**:

* [demo branch, with flips and insect-like turns](https://github.com/matejkarasek/paparazzi/tree/delfly_transformer_MXS_master/)
* [code used at IMAV 2018](https://github.com/tudelft/paparazzi/tree/transformer_imav): monocam, laser range sensor, WiFi

To **set up flips / insect-like turns / automated maneuvers** comment out (and adjust) the relevant settings at the top of:
* [sw/airborne/firmwares/rotorcraft/guidance/guidance_flip.c](https://github.com/matejkarasek/paparazzi/blob/delfly_transformer_MXS_master/sw/airborne/firmwares/rotorcraft/guidance/guidance_flip.c)
The current code only allows one type of maneuver to be used, e.g. either a roll flip, or a pitch flip, or a insect-like turn, etc.

**Devo 10 model**
* [model for the transmitter, 4-minute timer reset by AILE D/R](https://github.com/tudelft/paparazzi/blob/transformer_imav/devo10/model8.ini)
* [model for the transmitter, no timer, shows command % on all channels](https://github.com/matejkarasek/paparazzi/blob/delfly_transformer_MXS_master/devo10/model8.ini)

![DEVO10](https://github.com/tudelft/mavlab/raw/master/photos/drones/nimble/devo10_description_Transformer.png)
* Model for Delfly Nimble Demo: the transmitter file, new demo code and flight procedure in which you can now select a roll flip /pitch flip /evasive maneuver is shown [here](https://github.com/tudelft/mavlab/wiki/Demo-Delfly-Nimble)

<a href="#top">[Back to top]</a>

## Flight Procedure

Standard flight procedure:
* Turn on the transmitter, make sure the throttle stick is down, other sticks are centered, **all switches are at 0**
* Plug the battery in **while the Nimble is not moving** (e.g. on the ground/desk...). At startup, gyro biases are estimated, so it needs to be still.
* With MODE switch at 0 (RC Direct), try if pitching and rolling results in expected actuator responses
* Still in RC Direct, start flapping. Now you can also test the yaw actuator.
* Switch MODE to 1 (Attitude stabilization).
* In hand, test that the vehicle tries to counteract pitching and rolling motions.
* Increase the throttle to around 3/4 command, launch the Nimble, and have fun flying!
* Catch the Nimble / land
* Set throttle to 0 (stick down) to disarm, return to RC Direct by switching MODE to 0

Flips or insect-like turns
* The Nimble needs to be flashed with the appropriate code
* Make sure that RUD DIR switch is at 0
* While flying, Switch MODE to 2. The Nimble will stay in Attitude stabilization, but the flips/turns can now be triggered with RUD DIR
* To trigger a flip/turn, switch RUD DIR to 1
* Once the maneuver is completed, return RUD DIR to 0
* Repeat as many times as you want, and have fun!

Optitrack position control
* The Nimble needs to be flashed with the appropriate code.
* Once you get telemetry and 3D fix in GCS, double click on e.g. "stay p1" in the flight plan. Make sure it got activated.
* While flying near point p1, Switch MODE to 2. The Nimble will go to Navigation mode and will fly to and stay at the coordinates of p1.
* From now on, continue with your flight plan.
* To terminate the flight, catch the Nimble, set MODE to 0 and set the throttle to 0.

Troubleshooting
* The Nimble **does not start flapping**: make sure the roll/pitch/yaw sticks are centered and the trims reset. Sometimes, DelTang receiver readings are biased. In that case, check the telemetry and adjust the transmitter trims until you see zero RC commands in the telemetry.
* Once the battery is low, the Nimble starts behaving erratically: you are flying a Nimble without a power regulator, and the receiver is the first component to stop working when the battery voltage is low. Use a timer to stop flying early enough, or add a power regulator.
* The Nimble is **drifting**: make sure your autopilot is properly fixed and aligned with the airframe. If so, continue with the following two points.
* The Nimble drifts **forward/backward**: adjust the neutral dihedral servo position in the airframe file to trim the vehicle. Do not forget to adjust also the min/max accordingly.
* The Nimble drifts **left/right**: loosen / tighten the left / right wing by moving its root slightly up / down. More tension should give more lift, less tension less lift.

<a href="#top">[Back to top]</a>

## Scientific Papers and Thesis

* [The DelFly Book](https://www.springer.com/gp/book/9789401792073)
* [A Tailless Aerial Robotic Flapper Reveals that Flies Use Torque Coupling in Rapid Banked Turns](https://svn.lr.tudelft.nl/trac/MAVLAB/attachment/wiki/DelFly_Transformer/Karasek%202018%20A%20tailless%20aerial%20robotic%20flapper%20reveals%20that%20flies%20use%20torque%20coupling%20in%20rapid%20banked%20turns.pdf)
a lot is described in the supplement
* [A Minimal Longitudinal Dynamic Model of a Tailless Flapping Wing Robot for Control Design](https://iopscience.iop.org/article/10.1088/1748-3190/ab1e0b)
* [MSc thesis](https://svn.lr.tudelft.nl/trac/MAVLAB/attachment/wiki/DelFly_Transformer/Kajak_MSc_thesis.pdf)

<a href="#top">[Back to top]</a>


## Extra information
* [3D Models](https://github.com/tudelft/mavlab/wiki/3D-Models)
* [List of Components and Purchasing](https://github.com/tudelft/mavlab/wiki/Delfly-List-of-Components-and-Purchasing)
* [Connection Schematics](https://github.com/tudelft/mavlab/wiki/Delfly-Connection-Schematics)
* [Downloading logs from Micro SD card](https://github.com/tudelft/mavlab/wiki/SD-Card-Logging-and-Formatting)
* [OptiTrack tutorial for Delfly](https://github.com/tudelft/mavlab/wiki/OptiTrack-Delfly)

<a href="#top">[Back to top]</a>
