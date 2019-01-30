# DelFly Nimble (aka Transformer)

![Transformer](https://github.com/tudelft/mavlab/raw/master/photos/drones/nimble/DSC_0350-2_small.jpg)

## Paparazzi code
**The latest code (limited functionality)** will be soon in Paparazzi master (based on this [PR](https://github.com/paparazzi/paparazzi/pull/2380), allows basic flying + Optitrack flying):
* [DelFly Nimble airframe file, PPRZ master](https://github.com/paparazzi/paparazzi/blob/master/conf/airframes/tudelft/delfly_nimble.xml)

**Every Nimble might be different**, e.g. motors might be connected to different pins than in the master airframe, so always check before flying! 
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


## Flight procedure

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
* To terminate the flight, catch the Nimble, set MODE to 0 and set throttle to 0.

Troubleshooting
* The Nimble **does not start flapping**: make sure the roll/pitch/yaw sticks are centered and the trims reset. Sometimes, DelTang receiver readings are biased. In that case, check the telemetry and adjust the transmitter trims until you see zero RC commands in the telemetry.
* Once the battery is low, the Nimble starts behaving erratically: you are flying a Nimble without a power regulator, and the receiver is the first component to stop working when the battery voltage is low. Use a timer to stop flying early enough, or add a power regulator.
* The Nimble is **drifting**: make sure your autopilot is properly fixed and aligned with the airframe. If so, continue with the following two points.
* The Nimble drifts **forward/backward**: adjust the neutral dihedral servo position in the airframe file to trim the vehicle. Do not forget to adjust also the min/max accordingly.
* The Nimble drifts **left/right**: loosen / tighten the left / right wing by moving its root slightly up / down. More tension should give more lift, less tension less lift.


## List of components

|| autopilot || [Lisa/MXS](https://github.com/paparazzi/paparazzi-hardware/tree/master/controller/lisa_s/lisa_mx_s/v1.0) or [Lisa/S](https://wiki.paparazziuav.org/wiki/Lisa/S) ||
|| motors || 2 x DelFly BL motor, 22 to 25 windings ||
|| ESCs || 2 x MI3A or MX3A with BLHeli ||
|| servos || 2 x HK 5330 ||
|| radio || Deltang Rx31 sumPPM ||
|| telemetry (optional) || Wifi Esp8266 esp 09 ||
|| power regulator (highly recommended) || ask Christophe ||

Check the [wiki:delflyEquipment DelFly equipment page] for more details on how to flash BLHeli, how and where to order the motors, etc.

## Connection schematics

The standard connection schematics are in the following pdf:
* [Transformer connection schematics](https://github.com/tudelft/mavlab/raw/master/Transformer_connection_schematics_MXS.pdf)

And here the autopilot and SD card connections:


![Lisa MXS](https://github.com/tudelft/mavlab/raw/master/photos/drones/nimble/LisaMXS_transformer_connections_small.png)


Pay attention:
* in the latest code, the ADC 4 pin on the schematics was remapped as ADC 7
* in the latest code, the ADC 6 pin on the schematics was remapped as ADC 8
* stereocam / monocam / laser ranger might be connected to either Rx3 or Rx4, check in the code you're using

You might want to add a power regulator supplying constant 3.3V power to your receiver (highly recommended) and possibly to the autopilot. However, if you power the autopilot by the power regulator, the onboard voltage reading will stop working (you will see 3.3V all the time). To enable it, you need to rotate resistor R9 on the autopilot board and connect the battery voltage to its free end. Check the [schematics](https://github.com/paparazzi/paparazzi-hardware/raw/master/controller/lisa_s/lisa_mx_s/v1.0/lisa_mx_s_v1_0.PDF) of the Lisa MXS board, or ask for help if uncertain.

![Power Regulator](https://github.com/tudelft/mavlab/raw/master/photos/drones/nimble/power_regulator.jpg)


# Downloading logs from micro SD card
- the logging only works with <=2GB cards
- due to a [bug](https://github.com/paparazzi/paparazzi/issues/2092) only 43 logs can be written, than ALL the logs become unreadable, so keep this in mind and erase the card once in a while by formatting it via a PC card reader 
- to download the data via a card reader, use [this tool](https://github.com/tudelft/highspeedlogger/)
- download the code from github (e.g. 'download the zip'), build it with 'make' command, then go to /tools/bin/
- download the log from SD card by running 'sudo ./pprz_downloader /dev/sdb' or 'sudo ./pprz_downloader /dev/mmcblk0' (if none of the two work, check the device name with 'll /dev' after inserting the SD card into the reader)
- this creates binary 'sd_log_00000.bin','sd_log_00001.bin', etc. log files
- [this tool](https://github.com/paparazzi/paparazzi/blob/master/sw/logalizer/sd2log.ml) (part of your PPRZ installation) will convert the binaries into paparazzi logs
- go to 'paparazzi/sw/logalizer' and run './sd2log [path to the binaries]/sd_log_00000.bin'
- if you get errors, make sure your [environment variables](https://wiki.paparazziuav.org/wiki/Installation#Environment_Variables) are set correctly
- the paparazzi logs will be stored in 'paparazzi/var/logs' and can be viewed with the [paparazzi log plotter](https://wiki.paparazziuav.org/wiki/Plotter)
- [Matlab script](https://github.com/tudelft/mavlab/raw/master/scripts/read_pprz_MXS.m ] that loads the log into Matlab (if not working update according to messages.xml)



== 3D printed parts ==
- printed at [Shapeways](https://www.shapeways.com/)
- [STL file](https://1drv.ms/u/s!AiynX8wt2X_PkuBkiUyEsvkO_RJhmw) when printing in "Smooth Fine Detail Plastic" (previously "Frosted Ultra Detail"). High-resolution prints, but material brittle.
- [STL file](https://1drv.ms/u/s!AiynX8wt2X_PlpA5nCe68dNXT2Rdqg) when printing in "Black Professional Plastic". Resolution ok, but holes need to be drilled, gear models "inflated" by 0.04 mm to get the desired shape, the gear axis distance reduced by 0.05 mm.

== Complete 3D model ==
- [Solidworks model](https://1drv.ms/f/s!AiynX8wt2X_Ph4I-EseeEj9i3t0DWg )
- main assembly: Transformer.sldasm
- assembly for 3D printing: Transformer_to_print.sldasm
- assembly for 3D printing in "Black Professional Plastic": Transformer_to_print_black_final.sldasm

Should the above links stop working, the model can also be accessed on the network group drive (from TU Delft network, only for MAVLab employees):
* M:\lr\co\MavLab\018_Postdocs\2015-2019 Matej Karasek\SolidWorks\DelFly Transformer

== Scientific Papers & theses ==
* [[https://svn.lr.tudelft.nl/trac/MAVLAB/attachment/wiki/DelFly_Transformer/Karasek%202018%20A%20tailless%20aerial%20robotic%20flapper%20reveals%20that%20flies%20use%20torque%20coupling%20in%20rapid%20banked%20turns.pdf | The Science paper]], a lot is described in the supplement
* [[https://svn.lr.tudelft.nl/trac/MAVLAB/attachment/wiki/DelFly_Transformer/K_M__Kajak_Nimble_model_submitted.pdf | Paper on longitudinal dynamics modeling]] (submitted, do not share):
* [[https://svn.lr.tudelft.nl/trac/MAVLAB/attachment/wiki/DelFly_Transformer/Kajak_MSc_thesis.pdf | Thesis of K.M. Kajak]] 