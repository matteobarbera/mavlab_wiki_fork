## Flight Procedure

**Devo 10 model**

![DEVO10](https://github.com/tudelft/mavlab/blob/master/photos/drones/nimble/devo10_description_demo_Nimble_new.png)

Demo flight procedure:
* Turn on the transmitter, make sure the throttle stick is down, the other stick is centered, RUD DIR at 1 and MODE at 2, the rest of switches are at 0.
* Plug the battery in **while the Nimble is not moving** (e.g. on the ground/desk...). At startup, gyro biases are estimated, so it needs to be still.
* With MODE switch at 2 (RC Direct), try if pitching and rolling results in expected actuator responses
* Still in RC Direct, start flapping. Now you can also test the yaw actuator.
* Switch MODE to 1 (Attitude stabilization).
* In hand, test that the vehicle tries to counteract pitching and rolling motions.
* Increase the throttle to around 3/4 command, launch the Nimble, and have fun flying!
* Catch the Nimble / land
* Set throttle to 0 (stick down) to disarm, return to RC Direct by switching MODE to 2

Flips or insect-like turns
* The Nimble needs to be flashed with the appropriate code
* Make sure that RUD DIR switch is at 1
* While flying, Switch MODE to 0. The Nimble will stay in Attitude stabilization, but the flips/turns can now be triggered with RUD DIR
* To trigger a flip/turn, switch RUD DIR to 0
* Once the maneuver is completed, return RUD DIR to 1
* Repeat as many times as you want, and have fun!



Troubleshooting
* The Nimble **does not start flapping**: make sure the roll/pitch/yaw sticks are centered and the trims reset. Sometimes, DelTang receiver readings are biased. In that case, check the telemetry and adjust the transmitter trims until you see zero RC commands in the telemetry.
* Once the battery is low, the Nimble starts behaving erratically: you are flying a Nimble without a power regulator, and the receiver is the first component to stop working when the battery voltage is low. Use a timer to stop flying early enough, or add a power regulator.
* The Nimble is **drifting**: make sure your autopilot is properly fixed and aligned with the airframe. If so, continue with the following two points.
* The Nimble drifts **forward/backward**: adjust the neutral dihedral servo position in the airframe file to trim the vehicle. Do not forget to adjust also the min/max accordingly.
* The Nimble drifts **left/right**: loosen / tighten the left / right wing by moving its root slightly up / down. More tension should give more lift, less tension less lift.

<a href="#top">[Back to top]</a>