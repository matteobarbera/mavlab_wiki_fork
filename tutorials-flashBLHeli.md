# ''Instructions for BLHeli Rev 16''

Use BLHeliSuite Beta and Arduino Nano stick to program an ESC through the MOSI/MISO connection pins.
Download BLHeliSuite from https://blhelisuite.wordpress.com/ (This guide updated for `Rev 16.6.14.9.01`)

## Setup and Connections

Connect the Arduino Nano Stick, Esc, and the Power supply as shown in the figures below. Ensure the Arduino is flashed with a 4-way interface firmware. In case you need to initial flash/re-
flash an Arduino Nano board. Refer to Section” Create a NANO Stick for Flashing ESC”.
 - The flashing of ESC requires 3 wires and is done over a C2 interface. Here the wires will be marked in **Black, Red, and White circles**. Here, the Red and White lines indicate the signal lines and not Voltage supply line(V+), Black indicates ground.
 - The ESC can be powered externally, or from the 3.3V pin of the Arduino board (DO NOT CONNECT IT TO VIN = 5V !!!).
 - The Below figures show the pin configurations on the ESC and Arduino board along with the Circuit Diagram.

![Pincircles](https://github.com/tudelft/mavlab/raw/master/photos/blheli/Pincircles.JPG)

![Pincircles](https://github.com/tudelft/mavlab/raw/master/photos/blheli/Circuitdiagram.JPG)



## Create a NANO Stick for Flashing ESC.
 
 - In the **Make Interfaces** tab, ensure you have chosen the right COM port assigned to the Arduino Nano Stick. Ignore the baud rate as it is determined by the installed Arduino bootloader.
 - Click on **Arduino 4way- Interface** tab and choose the file named `4wArduino_Nano_16_PD3PD2v14302.hex` file for the above-mentioned Pin configuration (or the closest similar in the newer versions).
 - Click OK and wait until you see `Write successful` message. And you’re done. 

	
![Pincircles](https://github.com/tudelft/mavlab/raw/master/photos/blheli/s2.JPG)


## Flashing the ESC procedure: ==

 - Select `SILAB C2(4way-if)` under the `Select ATMEL/SILABS interface` as shown in below figure.
 - Select the appropriate COM Port to which the Arduino is assigned in the bottom left corner as shown below.

![Pincircles](https://github.com/tudelft/mavlab/raw/master/photos/blheli/S1.JPG)


 - Power up the Esc using Battery (or 3.3V pin on the Arduino) and Click on connect.
 - If successfully connected, a message is displayed, if not recheck the connections. 
 - Click on Flash BLHeli and choose the appropriate. hex file for the ESC. '''Use [https://svn.lr.tudelft.nl/trac/MAVLAB/wiki/electronics/BLHeliEnableRPMoutput this link] to get our modified hex file, which allows rpm sensing.'''
 - A warning might appear if a different BL Heli version is already flashed. 
 - Press OK and confirm to Flash the ESC. 
 - When asked if you want to write current settings, say no.
 - Change the settings to the following values:


![Pincircles](https://github.com/tudelft/mavlab/raw/master/photos/blheli/BLHeli_settings_DelFly.jpg)


 -  Click Write Setup to the ESC.
 - Click Read Setup to verify the values were written correctly. If not, repeat the previous two steps.
 - You are done.


## ''Instructions for previous BLHeli versions (obsolete)''

Use BLHeliSuite Beta and a Arduino Nano to program a ESC through the MOSI/MISO connection pins.

1. download BLHeliSuite from https://blhelisuite.wordpress.com/ (this guide is written for version 13.0.0.3)

2. connect the ESC to the Arduino, and the Arduino to the PC, see image below. The ESC is connected to the Arduino using the MOSI and MISO lines, Vin (3.3 volt) and a ground. Check the pdf 'BLHeli supported !SiLabs ESCs.pdf' in the BLHeliSuite Manual folder to see to which pads the MOSI and MISO need to be connected.

![Pincircles](https://github.com/tudelft/mavlab/raw/master/photos/blheli/IMG_20150219_152415.jpg)

3. In the 'ATMEL/SILABS' menu select 'SILABS serial interface'.

4. If needed, you can reflash the software to the Arduino Nano using the second tab in the BLHeliSuite ('Interfaces for Silabs'). Press 'Make Arduino Nano Stick' and select 'Arduino_Nano!__16_PB3PB4vxxxx' if using the MOSI/MISO pins to communicate with the ESC.

5. In the first tab, all the way down, select the right COM port and press 'Connect' to connect with the Arduino.

6. If successfully connected, read the current setup to see if the connection with the ESC is OK: Press the 'Read Setup' button below in the window. If you use a new ESC, it will give a warning message. 

7. Select the right settings by reading in the settings from the .hex you want to use. Go to 'BESC Setup > Read Setup From HEX File', and select the .hex file appropriate for the ESC you are programming.

8. Verify the settings, the recommended settings for DelFly are here: https://svn.lr.tudelft.nl/trac/MAVLAB/wiki/electronics/BLHeliDelflyParameterSettings

9. Press 'Flash BLHeli' below in the window. It will ask you to select the right version (I think it will read from the ESC which type of ESC it thinks it is dealing with). Press OK and then confirm to flash the ESC.

10. You're done!

