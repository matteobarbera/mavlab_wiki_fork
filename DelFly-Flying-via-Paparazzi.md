DelFly Desperado

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
## Small Signal Measurement

<a href="#top">[Back to top]</a>

# Autopilot

<a href="#top">[Back to top]</a>
# RF Link

<a href="#top">[Back to top]</a>
# GPS Antenna
# Actuators
# Weight
# Demonstration

<a href="#top">[Back to top]</a>

# Flight Plans
## Tests
## Final
<a href="#top">[Back to top]</a>
