# Motor Testbench

[Sourcecode to be found here on SVN](https://svn.lr.tudelft.nl/MAVLAB/MavBal/MotorTestBench)

This page is about the workings and usage of the Motor Test Bench (MTB). For visualing the data, go to the Motor Data [Visualizer page](wiki:motorDataVisualizer).

> * **WARNING: THE TORQUE SENSORS ARE EXTREMELY FRAGILE DUE TO THEIR HIGH SENSITIVITY AND ARE VERY EXPENSIVE TO REPAIR**
> * **DO NOT TOUCH THE MAGNETIC DISCS ATTACHED TO THE TORQUE SENSOR.`**
> * **DO NOT APPLY ANY LOAD ON THE MAGNETIC DISCS OTHER THAN NORMALLY MEASURING A MOTOR`**
> * **DO _NEVER_ USE ANY METAL TOOLS IN BETWEEN THE DISC AND SENSOR. ALWAYS REMOVE THE MOTOR FROM THE STAND FROM THE BACK SIDE (PLASTIC SCREWS) BEFORE CHANGING THE ALUMINIUM DISC.**


# Introduction

In order to optimize the design of the BLDC motor and motor controller a setup is needed to independently
and accurately measure the performance. The extraordinary
operating range of the motors used in the Delfly exclude commercially available motor test equipment.
Therefore, a motor test bench (MTB) was developed in-house at the TU Delft by Rick Ruijsink to enable accurate measurements
of motor characteristics unique to this operating regime. The MTB is capable of measuring the most
important parameters of a motor: torque, RPM and electric input (voltage and current). Two test benches have been
developed: a small one is designed for motors in the range a few Watts (like the BLDC motor used
on the Delfly ) up to several tens of Watts, and a larger one designed for motors up to 300 Watt
output power at 15.000 rpm.

# Working principle

The MTB’s working principle is based on the same principle as the Eddy current brake. An aluminium disc
mounted on the motor axle spins at a distance in front of another disc with permanent magnets, which is
attached to a torque sensor. The permanent magnets induce eddy currents in the rotating aluminium disc
due to Faraday’s law of induction. By Lenz’s law, these eddy current will create their own magnetic field which
opposes the field of the magnets. This will cause the aluminium disc to experience a drag force, i.e. torque,
which opposes its motion, proportional to its velocity.
The reactionary torque on the magnet disc is measured by the torque sensor. The magnitude of the
induced current in the aluminium disc is dependent on the distance to the magnetic field. This means that the torque on the motor
can be varied by varying the distance between the aluminium and the magnet disc.
The electrical energy of the eddy currents is dissipated as heat due to the electrical resistance of the conductor.

# Setup overview 

<img src="../raw/master/photos/motortestbench/MTBLoverview.jpg" width="50%"/>

The setup consists of a motor mount made of glassfiber, which is non-magnetic. A configuration of holes
is drilled into the mount to accommodate a wide range of motor mounting types. 
An aluminium disc can be mounted to the axle of the motor, in which the eddy currents will be induced.
In front of the aluminium disc sits the magnetic disc. It consists of a plastic disc holding 12 powerful
neodymium magnets mounted to an aluminium disc. The magnetic disc is fixed to a torque transducer, the
[http://www.lorenz-sensors.com/pdfdatbl/m/080559n_d-2452.pdf D-2452 (series 712)] by !LorenzMesstechnik GmbH.
The whole magnetic disc / torque transducer assembly is mounted on a linear slide. This allows the gap
between the magnetic and aluminium disc to be varied manually by turning an adjustment knob, thereby
decreasing or increasing the load on the motor. The output signal of the torque transducer is transferred to a custom made PCB which conditions the signal to
be collected by the data acquisition device (DAQ). Other signals that are available to the DAQ are the voltage,
current and motor temperature.
The DAQ is the USB-6009 made by National Instruments. !LabView is used to process
the data and generate a visual representation as well as providing logging of all signals.
For each input voltage and PWM value of the controller the input power (i.e. voltage-in and current-in) can
be measured along with the resulting torque and motor speed from which consequently the efficiency of the
motor can be calculated.
By changing the distance of the air gap the performance curves for that input voltage and PWM value
can be derived. This can be repeated for any combination of input voltages and PWM values, resulting in a
complete performance characteristic of the motor.
The torque of the motor shall not be higher than the maximum torque limit of the sensor. The power,
torque times speed, is not limited by the sensor but it is important to monitor the heat generated in the aluminium
disc. For high power measurements the measurement time shall be kept short to avoid overheating.

Please note that the currently included thermometer is not very suited to small outrunner motors due to its size. It also has a large heat capacity so it is a bit slow.

# Specifications
## MTB Small

||  ||'''Value'''||'''Unit'''||
|| Resolution   ||0.001||mNm ||
|| Accuracy     ||0.005||mNm||
|| Maximum torque 	||5	||mNm ||
||Maximum Voltage	||15	||Volt||
||Maximum Current Cont.	||7	||Amp||
||Peak Current          ||10	||Amp||

## MTB Large

|| ||'''Value'''||'''Unit'''||
||Maximum torque 	||200	||mNm||
||Maximum Voltage	||25	||Volt||
||Maximum Current Cont. ||36    ||Amp||
||Peak Current	        ||50	||Amp||

# Using the MTB

## Software

You need Labview 2015 and the DAQmx driver for the USB-6009 DAQ. Both can be found on the National Instruments website.

The Labview software for the MTB can be found on our SVN: https://svn.lr.tudelft.nl/MAVLAB/MavBal/MotorTestBench

The main program for using the motor testbench is: main.vi.

There are multiple folders in the Motor test bench folder:

* addaxis6 - used by the visualisation .m file "plotResults.m". For more advanced ways of plotting the data, please refer to the [wiki:motorDataVisualizer Motor Data Visualizer page].
* arduinoMini - contains the sourcecode for the Arduino Mini that generates the PWM pulses based on a 0-5V input signal.
* documentation - contains background design files, calibration documents and background on the aerodynamic corrections.
* measurements - the measurements you log from Labview will be saved in here. If this folder is not present, Labview will give an error when you try to log.
* subVI - contains supporting .vi's for the labview software.

## Hardware

The hardware includes the following:

1. Texas Instruments USB-6009 DAQ
2. MTB
3. Double headed USB cable to connect the DAQ to the PC and supply the MTB sensor board with 5V.
4. Lab power supply with power cable.

Two alumunium disc with several collets for different axle diameters (0.6 mm to 1.5mm) are available, as well as several motor mounts with different interfaces.

There are two ways of speed sensing available. Sadly there is only one digital input pin on the DAQ (pin #29), so when you want to change input, you have to rewire it. The green wire is for the phase sensor, the white wire for the optical sensor. Two images of the wiring to the USB-6009 are included at the end of this page for reference.

# Running a test

After running the main.vi, you first have to set the correct settings.

<img src="../raw/master/photos/motortestbench/mtbsettings.JPG" width="100%"/>

**Invert torque direction** - inverts the torque signal for when the motor spins the other direction.

**Measurement averaging window size** - the window size in number of samples of the time averaging. The main loop runs at 10Hz, so 40 samples would take 4 seconds.

**Aerodynamic drag correction**  - the aluminium disc experiences aerodynamic drag which is corrected for in software. Only the small discs for the small MTB are currently implemented.

**Config file** - select the right config file to be loaded depending on which MTB you are using (small or large). The main.vi needs to be stopped and started for the settings to take effect.

**Speed sensor** - two different speeds sensors are available to be connected to pin 29 on the DAQ, an optical and a electrical one. When using the electrical phase sensing option, you need to provide the number of poles of the motor. This is the number of magnets divided by 2. Note that this only works for brushless motors.

Before running a test you should calibrate the torque sensor. Also enter a filename, or one will be chosen automatically. If you enter the file name of an existing file, new data will be apended to the end of it.

In the left of the screen you can set PWM throttle setting. Only steps of 10% are possible, and the output PWM runs from 1000us to 2000us. The six plots show the measured variables. On the right you can see the result of your measurements. Additional points are added to the graph with each measurement you take and you can select which data you want to have shown on the X- and Y-axis.

You can change the load on the motor by changing the distance between the sensor and the spinning disc.

# Reference 

## Calculations

### Input
	||Voltage_in||(dV)||Differential Analogue||
	||Current_in||(V_I)||Single ended Analogue||
	||Speed (commutations)||(Hz)||Digital Pulse (event counter)||
	||Torque||(dV_T)||Differential Analogue||
	||Torque reference voltage||(dV_TRef)||Differential Analogue||
	||Temperature (motor)||(°K)||Single ended Analogue||

### Output
	||PWM||[V]||reference voltage [0-5V] for the Trinket to generate a pulse train between 1000 and 2000 micro second. See trinket code in the SVN repos||

### Calculate at constant voltage and PWM value (averaged values)
photo
	||Torque = ||(dV_T / dV_TRef) * k_T||[mNm]
	||Currentin = ||V_I * k_I	||[A]
	||Speed = ||Hz/(n_poles/2)	||[rps]
	||Powerin = ||dV * I	||[W]
	||Powerout = ||Torque * 2 * pi * rps||[W]

k's are machine constants (defined in config file),
	||'''variable''' || '''name''' || '''MTB small''' || '''MTB large''' ||
	||torque gain||k_T || -4.97725 || ???? ||
	||current gain||k_I|| 1 || ???? ||
	|| number of poles (motor dependent!) || n_poles || motor || motor||

## Config files

Both motor testbenches have a config file which defines the relationship between the voltages that are measured and its physical representation. They are called 'configMTBsmall.ini' and 'configMTBlarge.ini'. The values in these don't need to be changed.

## Wiring

Analog
1. Ground
2. + V Motor
3. - V Motor
4.  Ground
5. + 5 Volt Reference Torque
6. - 5 Volt Reference Torque
7.  Ground
8. + Torque
9. - Torque
10. Ground
11. + Motor Current
12. Temp

Digital 
29. RPM Pulses

<img src="../raw/master/photos/motortestbench/MTBconnectorTo6009.png" width="50%"/>

<img src="../raw/master/photos/motortestbench/IMG_20150611_133744.jpg" width="50%"/>
<img src="../raw/master/photos/motortestbench/IMG_20150611_134908.jpg" width="50%"/>

----
# Motor Data Visualizer

To visualize the data from the MTB?, a GUI visualizer was created using MATLAB. The software and measurement data can be found at:
SVN: 	​https://svn.lr.tudelft.nl/MAVLAB/MavBal/motorlibrary
Usage

    In folder mfiles, open the GUI.m file
    Run the m-file by pressing F5 

# Information

The visualizer can show up to 4 data sets, with one parameter on the x-axis and up to 4 on the y axis.

The Delfly load characteristic can be loaded with the checkbox 'Show Delfly35 characteristic'. This data is taken on a Delfly with 28 cm wingspan and a Delfly35W motor. Note that for the torque / RPM profiles, it shouldn't matter which motor was used to measure its characteristics, only the wingspan.

The data of each measured motor is stored in files which are sorted by the voltage they were measured at (3.4V, 3.8V or 4.2V), or a certain thrust setting (50%, 75% or 100%). The files are named accordingly.

If you have measured new motors, the data should be stored in the raw_data/MTB folder. The following naming scheme is used:

Motorname_ESCname_ESCsoftwareVersion_voltage_thrustsetting.log

The voltage ends always with a 'V', the thrustsetting is followed by 'proc' for percent.

For example:

 Delfly18W_MX3A_BL13_34V_100proc.log

# TODO

* When plotting more than two variables, the tick labels are overlapping on the y-axis. For the 3rd and 4th variable, its whole respective y-axis should be shifted outside in order not to overlap.
* Selecting a motor can become difficult if too many motor datafiles are present. So when the data set increases, a more intuative way of selecting data files should be implemented. 
