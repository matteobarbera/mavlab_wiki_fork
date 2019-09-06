DelFly Desperado

Editing note: If any link on this page can't be open, it's because the original link on the svnlr doesn't work.

- [Outcome](#outcome)
  * [Additional](#additional)
- [Deliverables](#deliverables)
- [Spefifications](#spefifications)
- [Description](#description)
- [Ubuntu Trick](#ubuntu-trick)
- [ESC](#esc)
  * [Speed Measurement](#speed-measurement)
  * [Simon K](#simon-k)
  * [Small Signal Measurement](#small-signal-measurement)
- [Autopilot](#autopilot)
- [RF Link](#rf-link)
- [GPS Antenna](#gps-antenna)
- [Actuators](#actuators)
- [Weight](#weight)
- [Demonstration](#demonstration)
- [Flight Plans](#flight-plans)
  * [Tests](#tests)
  * [Final](#final)

# Outcome
Fly a newly designed Delfly ouside with 5m/s wind fully autonomous via GPS.
## Additional
If time permits:
* Combine navigation with vision
* Make a great video about the development and outcome
* Slow stream 80x60 image to ground

# Deliverables
1. DelFly with Lisa/S and ESC build
1. Opensource ESC
1. Documentation

<a href="#top">[Back to top]</a>

# Spefifications
* Name: Delfly Desperado AOW 
* Weight: ?
* Range: 1500m 
* Speed: Max speed 6m/s 
* Ceiling: 2k/m

# Description
A fully 10 DEg IMU accelo, gyro, magneto, baro with GPS and autopilot electric engine flapping wing

# Ubuntu Trick
It might happen that when plugging in the black magic probe or the Superbit rf dongle that it takes around 30 seconds to get them working. This is because modem-manager is trying to convert the newly plugged device to a UMTS or a GSM device. You can remove the modem-manager package to remove that comportment and get your device working immediately.

This can be debugged by searching for the deamon using the device using the command: `sudo lsof`. That command displays all the files used (opened) and the application using it. We then can apply it to our device: `sudo lsof | grep "/dev/ttyACM0"`.

The building of the DelFly is described in the tutorial [attached]() to this page.

<a href="#top">[Back to top]</a>

# ESC
How to get the startup of the DelFly (more power at boot and faster flapping frequency) (also in the config file of the board):
* DEFAULT_PGM_MULTI_STARTUP_PWR do change a lot on the startup.
* DEFAULT_PGM_MULTI_STARTUP_ACCEL change a little bit
* DEFAULT_PGM_MULTI_STARTUP_RPM change mediumly.

Flapping rate:
* P and I doesn't seams to be changing much.
* DEFAULT_PGM_MULTI_GAIN : seams to make the boot up of the motor easier
* DEFAULT_PGM_MULTI_DEMAG_COMP : desable or low seams to be the same. High is making thingth worth.
* DEFAULT_PGM_MULTI_COMM_TIMING : doesn't seams to change much. A value of 3 (or less) seems to be the best.

The method used by the BLHeli firmware to figure out the next zero crossing event is by doing integration on the last 4 commutation timings. That means the timing of the last low then high then low then high then low, only two pulses in total, but two times low and two times high.

You can certainly remove some waiting at the startup of the ESC (line 5942).

## Speed Measurement
To measure the speed of the DelFly and its flapping rate, we can use an eagle tree brushless RPM sensor. This sensor seems to be generating 1 pulse per pulse sent to the motor. Knowing that we got 5 magnetics pairs in the motor of the DelFly and a gear ratio of 21.33 motor rotation for one flapping cycle, we got a total reduction between the output of the sensor and the flapping rate of: 1*5*21.33 = 106.65. We got 106.65 pulses going to the motor for each flapping cycle. (all of the calculation are made with the DelFly at full throttle).

Without any wings, the DelFly can actually run at 40 flaps per seconds.

## Simon K
We can program Simon K on an ATMEGA ESC like ​UEBD 6A from [HobbyKing](https://hobbyking.com/en_us/?gclid=Cj0KCQjwh8jrBRDQARIsAH7BsXfjh4wO-MoGpgR3amsScYz6rNlEtA_kRhUHqE8enST4sKJuU8xqRp0aAhkjEALw_wcB&gclsrc=aw.ds). By default, we get 20.4 flaps per seconds

## Small Signal Measurement
It is possible to amplify a small signal to make it usable on an oscilloscope for example. For that, we need to an instrumentation amplifier (use 3 operational amplifiers) or a Differential amplifier. That last one is well explained [here](https://en.wikipedia.org/wiki/Operational_amplifier_applications#Differential_amplifier_.28difference_amplifier.29).

<a href="#top">[Back to top]</a>

# Autopilot
The Lisa/S will be used as an autopilot. The old version of the Lisa/S has a strange programmation connector (cf attachment).

Random tips:
* To program the Lisa/S, use a USB port that does deliver some power (like a USB3 for example). You might get some errors (like unable to erase the flash memory) because the usb port in which the black magic probe is plugged doesn't deliver enough current.
* Plug the black magic probe first into the computer then connect it to the Lisa/S. The other way around doesn't seams to be working (no idea why).
* Restart the Lisa/S in order to get the new firmware running on it.
* The servos' output of the Lisa / 0.1 version is mismatched. The 1 and 2 are in fact the servo NO.4 and 5 (if you add the `<define name="USE_SERVOS_1AND2"/>` in the airframe file). Then the pins 3-6 are corresponding to the servos 0-3.

To make the Lisa/S bind to something: Configure everything in DSM2 mode (for a starter you are certain of what you need to configure that way). In the airframe file you need to add :

`<define name="RADIO_TRANSMITTER_PROTOCOL" value="DSM_DSM2_2"/>`

Unplug the power, press binding button, power up, let the binding button go. Wait a few seconds, then put remote in binding mode. The new driver for the superbitrf uses a LED to indicate the status of the communication (on the Lisa/S that LED is the yellow one (on the edge of the PCB) :
* One blink every few seconds: binding mode, searching for something to connect to
* Blink fast: synchronizing with something
* Steady: connected and talking with something

To get the IMU (accelerometer, gyroscope, and magnetometer) right, use the body_to_imu constrains in your airframe file. To know the right orders and signs, follow the instructions [here](http://wiki.paparazziuav.org/wiki/ImuCalibration#Accelerometer:).

To get the barometer working, you need to specify in your airframe file to get the values from the captor using the statement: `<define name="USE_BARO_BOARD" value="TRUE"/>`. Then we need to tell paparazzi to actually use the values it gets from the captor with that statement: `<define name="USE_BAROMETER" value="TRUE"/>`.

To automatically bind to a remote control, you can use the `<define name="RADIO_TRANSMITTER_ID" value="1974942194"/>` statement into the radio block of the airframe file. The value of that definition might be available using a USBRF dongle in debug mode and adding some debug messages line 365 of the firmware of it (in src/protocol/dsm_mimt.c).

<a href="#top">[Back to top]</a>

# RF Link
The old RF (the small green one) is produced by [DelTang](http://www.deltang.co.uk/). But it was an rf link specifically designed for the MAVlab so it is hard to find the exact same reference.

<a href="#top">[Back to top]</a>

# GPS Antenna
We will start off with an Atenova. We got 5 types of antennas:
* The big brown square: 4.70g
* The small grey square: 2.76g
* The small brown square (MIA-GPS-10): 3.07g
* The green PCB : ~1.2g : [Taoglas site](https://www.digikey.com/product-detail/en/ALA.01.07.0095A/931-1014-ND/2332641)
* The blue PCB Atenova A10137: ~ 0.9g
* The blue PCB Atenova A10204: 0.46g

Part number of some of those antennas:
* AP.10F.07.0039B from Taoglas
* ALA.01.07.0095A from Taoglas
The green PCB antenna was the final one chosen for the project. Using the last version of the Lisa/S (1.0) we are able to get a fixe at 4m in less than a minute. Those antennas are very fragile, so fragile that then sometimes are broken when they arrive (1 broken out of 3 bought).

<a href="#top">[Back to top]</a>


# Actuators
2.4ghz [SuperMicro]() Systems - [Double Linear Servo](https://www.ariesrc.gr/9482-origin-double-linear-servo.html) The driver for those servos in paparazzi is described [here](https://wiki.paparazziuav.org/wiki/Subsystem/actuators#Dual_PWM).

Specs: 
* Size: 33.35mm x 15.25mm 
* Height 7.80mm 
* Weight: 2.0g (wires not included) 
* Torque: 35g @ 4.2V 
* Speed: 0.12s @ 4.2V 
* Voltage: 3.0V~4.2V

These actuators have a latency of around 71ms with a Lisa/S controlling them. When we move the stick of the remote to one side, the servos start moving 71ms latter. In the same way, when the stick of the remote hits the maximum value, 71ms latter the actuator hits its own limit. Those measurements were done using a GoPro 3 running at 240fps. The actuator had a small load (a DelFly yaw aileron).

Those servos (HobbyKind Ultra Micro Servo 1.7g for 3D Flight) are really good. But they are heavy. it is possible to easily cut two of the tags on the side (used for attachment), we can change the wires, and remove the metal cover of the slider. But even then we are still around 1.5g. The issue is that the motor is too big. But the mechanique is awesome. It would be nice to change that motor with a smaller one (for example from the red servos which are smaller).

<a href="#top">[Back to top]</a>

# Weight
cf array attached to the page.

# Demonstration
On a nice morning with max 5m/s wind a 500m route away (2minutes) an 8 pattern for 1 minute then back (2 minutes)

<a href="#top">[Back to top]</a>

# Flight Plans
## Tests
* Circle Standby
* Fly 8 pattern
* Flyroute AB and back
* Autoland

## Final
* Takeoff with hand-launch detection
* Fly 2x circle
* Fly Path to end
* Fly 8 pattern
* Flyroute back
* Autoland

<a href="#top">[Back to top]</a>

# Attachments
[Link](https://svn.lr.tudelft.nl/trac/MAVLAB/wiki/delflyFlyingViaPaparazzi#no1)
