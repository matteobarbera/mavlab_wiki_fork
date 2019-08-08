[[PageOutline(1-2,Main)]]

# MAVBAL # 

The MAVBAL is a high accuracy, high resolution 6-axis balance to measure micro forces at a high rates. It is equipped with the ATI Nano17 Titanium force/torque sensor with the most sensitive calibration:
http://www.ati-ia.com/products/ft/ft_models.aspx?id=Nano17+Titanium

It can be used as a table top device, or in a windtunnel, together with an integrated tilting mechanism.

The setup consists of a balance, a National Instruments FPGA sampler and a user interface written in !LabView. The software is installed on a dedicated laptop (very slow...) and on Dell Precission laptop, also known as Guido's laptop (recommended, if available). You can also install !LabView on your own laptop, together with the FPGA related additions. 

##   Getting the software ==

The !LabView project, as well as software for controlling the !DelFly frequency and for tilting the sensor is on the SVN:

||SVN:||https://svn.lr.tudelft.nl/MAVLAB/MavBal/||

## Using the force balance ==

=## Login information for the old laptop ===
User name: **localadmin**

password: **Welkom01**

Even if you work with a different laptop, make sure you are using a static IP: 10.10.1.3

With subnet mask: 255.255.255.0

=## Start !LabView Interface ===
1. Launch !LabView, open project MAVLab.lvproj  (located in D:\MAVBal\DelFlyAcquisition_PWM+rpm at the time of writing)

2. The acquisition parameters need to be set first in Utility – Configuration File Generator.vi
||||||# Acquisistion parameters =||
|| Sample rate (Samples/s)	||	Reads to save	|| Max samples per read tested and working ||
||2000 || 1 || 9000 ||
||5000 || 1 || 14000 ||
||10000 || 1 || 19000 ||
||16667 || 1 || 16667 || 


3. Once all is set, run the VI to generate a config.xml file for the CompactRIO real-time controller

4. To load the xml to the FPGA, use ftp client, e.g. Filezilla (10.10.1.40, anonymous) and copy the xml to the root (there should be an old config.xml, which should be overwritten).

5. Run: MAVBAL-cRIO (10.10.1.40) >> RT Main.vi from the Project Explorer. Click save if it asks you so.

6. Also run My Computer >> UI_Main.vi 

## Use the software ==

1. Press 'Connect' to establish a connection with the FPGA.

2. Press 'Acquire live data'. You should start seeing data on the screen now. There is a big delay of seconds, and sometimes the screen will be blank.

3. Check if the signal changes if you (carefully) apply a force to the sensor.

4. Press "Bias" to zero the force and moment signals.

5. You can show and hide channels on the right, by right pressing on a legend entry, and select 'Hide/show' (correct?).

Each Mod corresponds to a physical module on the national instruments. So Mod3/ai0 is Module 3, input ai0 (analog in 0).

In a normal setup:

mod3/ai0 is voltage
Mod5/ai0 is current


6. Click 'Log Data' to record your data. This will collect a number of samples as specified in the configuration file you uploaded to the FPGA previously.

7. To collect the data, again use ftp. All the logfiles are in the Data folder, with a date- and time-stamp in the filename. 

8. Use the matlab routine to read the .tdms file. A basic .m file is attached to this page. This includes calculating the frequency from the Hall sensor.

## Lab power supply with sensing ==

1. Switch on the lab power supply.
1. Connect two wires between the points you want to regulate the voltage (see image). This might take a few tries to get right.
1. Put the polwer supply in sensing mode (see image).
[[Image(senseVoltWiring.jpg, width=500)]]
1. When the power is enabled, the Lab power supply will maintain the voltage at the remote sensing location. This means the voltage can be increased at the source, so make sure the equipment can handle this increased voltage.

# Data retrieval =

You can download all the logdata via FTP. On the data acquisition laptop, !FileZilla is already installed.

In case you are using other software, or installing it on your own laptop, these are the settings:

||Host || ip-address found in project explorer (10.10.1.40)||
||Port || Empty|| 
||Encryption || Using plain FTP ||
||Logon Type || Anonymous ||

# Data processing =

A MATLAB script is available that can extract the data from a .tdms file and plot the results. 

https://svn.lr.tudelft.nl/trac/MAVLAB/attachment/wiki/resources/mavbal/force_balance_processing_2016_06.m

# Reference =

Standard wiring to the NI cRIO:

[[Image(wiringMAVBAL.jpg, width=500)]]