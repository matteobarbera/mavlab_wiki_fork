# Lab Standards

# About

## Why

To enable everyone to focus on their research or studies and not to be bothered by some hard and software details, we adhere to some standards.

## How - Inventory

## What

## Benefits

The benefits of some form of standardization

## Contra Standardization

Not in all cases standardization and be adhered to. Why not? The lab is in the forefront of new development that also means new types of hardware and software must be used. Still where standard components *can* be applied, they *must* be applied.

# Procedures

* Papers
* [Videos](videos)
* PR
* Public appearance

# Materials

# Suppliers

We try to keep the same suppliers if possible. Note that with very specific parts, we just need a supplier who can deliver those againt a fair price.

Whatver the case try if you can buy via:

1. Farnell
2. Conrad
3. Hobbyking
4. ...

# OS's

RFC, more can be added of specific need

* Ubuntu 16.04 64 bit
* Ubuntu 18.04 64 bit
* Ubuntu 18.04 64 bit
* Ubuntu 32/64bit if embedded
* MS Win10 64Bit

All OS's **must** be set to English GUI language, this make life easier if one needs to cooperate with team members.

# Hardware

## Airframes

First to be said if you develop new control, new airfoils, other new stuff, no need to adhere to any airframe standard

But if you use the airframe to perform other control research or vision base experiment we have

* Bebop1
* Bebop2
* Mambo
* Disco
* Trashcan
* Crazyfly2

## Battery Charging

Empty battery? Battery charging only in charging areas. In the lab 0.44 we have one, the big shiny cupboard. In the Cyberzoo we have one, look for the text on the tables.

## Battery Storage

After your Work-week is over, one *must* put the used LiPo batteries in storage mode voltage. For this there are several battery storage (de)chargers. Also a regular charger has a Storage mode.

## Battery Connectors

If you are confused about if it is a male or female connector, it is not about the plasic, it is about where **metal is inserted in metal**, remember this and you can figure it out.

### 1s LiPo 

For 1s LiPo **three** different types of connectors are allowed

Note: If you happen to come across swapped polarity at battery side one **must** correct the battery. If wrong polarity at Drone side one **must** correct it at the drone side.

1) Molex Picoblade

<img src="../raw/master/photos/standards/connector_JST_DS_2.0mm_2Pin_M_F_aka_LOSI.jpg" width="25%"/>

For on very light and  tiny airframes like the Delfly.
 
2) JST PH2.0

<img src="../raw/master/photos/standards/connector_JST_2_pins_battery_side_female.jpg" width="25%"/>

On e.g. Eachine Trashcan airframe

3) JST-DS 

<img src="../raw/master/photos/standards/connector_JST_DS_2.0mm_2Pin_M_F_aka_LOSI.jpg" width="25%"/>

JST-DS 2.0MM 2-Pin Connector also known as a LOSI connector

On e.g. the Bitcraze Crazyflie airframe.
 
### 2s LiPo

<img src="../raw/master/photos/standards/connector_jST_RCY_battery_side_female.jpg" width="25%"/>

Only one type is in use, if not change the connector to a JST RCY Connector

### 3s upto 6s LiPo

For 3s to 6s battery connectors: XT60. Note that in 10sec burst the XT60 holds 150A! and continuous 60A

<img src="../raw/master/photos/standards/connector_XT-60_female.jpg" width="25%"/>

### 6s upto 12s LiPo

For 6s upto 12s lipo battery connector use a: XT90

# RX Receivers:

THe Lab has Standardized on FrSky RX or FrSky compatible RX

Which: R-XSR
Why: Good range, telemetry return option, open protocol, cheap, available, open software flash-able
How: Buy a bunch
What about ultra light airframes like the DelFly?: FrSky XM with CPPM or Sbus out these ones can replace the current deltang RX

All receivers must adhere to new EU rules LBT ETSI v1.8.1
ALL receivers in the lab should be FrSky or compatible, if not the AC should get another RX

# RX behaviour

# RX Output signal
## RX indication light colors

# RX FIRMWARE

If using an R-XSR the Firmware **MUST** be [v190311 EU LBT](https://github.com/tudelft/tx_configs/raw/master/taranis_x9dp_se/fs/FIRMWARE/R-XSR_LBT_190311.frk), reflash possible via STK module or via a Taranis X9D transmitter with specific flashing cable in the transport box.

# Data Transmission

## Wifi based small ESP8266(85) module [*MUST* use this firmware](https://github.com/paparazzi/esp8266_udp_firmware)

## Build in WiFi

## XBee Pro S1

<img src="../raw/master/photos/parts/tranceiver-xbee-pro-s1_01.jpg" width="25%"/>

[*MUST* use Firmware version 10EF - XBee 802.15.4](https://www.digi.com/products/embedded-systems/digi-xbee/digi-xbee-tools/xctu) 

## Herelink

<img src="../raw/master/photos/parts/tranceiver-herelink-onboard-module-01.jpg" width="25%"/>

[*MUST* use Firmware v0.2.2 or higher](https://github.com/CubePilot/cubepilot-docs/blob/master/herelink/firmware-releases.md)

## Si10xx
Modem Si10xx 868/900 based modems, So *not* the new RFD900_emp32
**Connector modem-side RP-SMA female** for signal out, meaning **antennas** must have a RP-SMA **Male**
[*MUST* use this Firmware](http://) 

## Telemetry FrSky

Whenever RX telemetry output is not needed, 99% of cases, it should be disabled in RC transceiver this to minimize telemetry over 2.4Ghz interference.

# OS's

## Ubuntu 16.04.x, 18.04.x, 20.04.x
In 64Bit, or if on 32Bitonly MCU, the 32bit variant

## Windows
Only Windows 10 64Bit, or a windows version that is supported by the TU IT department

# Markup: 

**Markdown**, Github extended syntax allowed.

# Autopilots

There are many...so our default RFC:

# Pixhawk Clones 2.4.8 - 
Why: Versatile, Well flexible, Available and cheap
# Pixhawk 4 - 
Why: Versatile, Well flexible, Available
# Pixracer v1.0 R14 and R15
Why: robust, versatile, available, cheap, hardfloat F4, SD card
# Lisa MXS: 
Why: Fits certain projects light small
# Parrot based boards ARDrone2, Bebop, Bebop2, Disco: 
Why: No need to build something, cheaply available
# Crazybee F4 Pro board v2.1 or higher
Why: complete, light, cheap, available, hardfloat F4. cc2500 chip usable for mesh networks

# Web technology: 
Lamp server

# CMS 
Wordpress, if need custom plug-in by student but made open to public

# Version control

* **Git** v2 or higher, and for old SVN repositories an Git SVN extensions can be used

# Basic Software 

Software used should have at least a Linux,optionally a Windows and OSX, version.
Exception are very specific programs for hardware, e,g. certain measuring equipment

* Visual Studio Code (WXL)
* KiCad  (WXL)
* FreeCad (WXL)
* Dia (WXL)
* Xflr (WXL)
* Inkscape (WXL)
* Gimp (WXL)
* LibreOffice (WXL)
* ? qelectrotech https://qelectrotech.org
* ? https://sourceforge.net/projects/tinycad/
* Motive v2.x (Optitrack)

One is free ofcourse use other software, only there is likely no one in the lab who can help you out if you have questions.

# Google services
Sadly not open, but access to all your data pragmatic for the time being

# Hardware PCB/schematic designs AP

* Current From EAGLE to KiCAD wherever feasible
In some scenarios Altium v19 may be used

# RC transmitters

* Taranis X9D [Firmware XJT EU LBT and OpenTX 2.3.1.x with fixed RSSI warning]()
* Taranis X-lite [Firmware XJT EU LBT and OpenTX 2.3.1.x with fixed RSSI warning]()
* SM600 Special Edition: PC USB "joystick type" RC transmitter SM600

End of life:

* Devo 10 : pull the last release from https://github.com/tudelft/tx_configs
* iRangeX 4in1 Multi-module in other TXs with MAVLab firmware to be found here:
* Hobbyking USB joystick