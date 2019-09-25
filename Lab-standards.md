# Lab Standards

# About

## Why

To enable everyone to focus on their research or studies and not to be bothered by some hard and software details, we adhere to some standards.

## How - Inventory

## What

## Benefits

The benefits of some form of standardization

## Contra Standardization

Not in all cases standardization and be adhered to. Why not? The lab is in the forefront of new development that also means new types of hardware and software must be used. Still where standard components can be applied, the *must* be applied.

# Procedures

* papers
* videos
* PR
* public aperance

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

Battery charging is obliged to take part only in charging areas. In the lab 0.44 we have one, in the Cyberzoo we have one.

## Battery Storage

After your Workweek is over, one *must* put the use batteries in storage mode voltage. For this there are several battery storage (de)chargers

## Battery Connectors

* 1s, three different types

* {TODO} for on very light and  tiny airframes
* On e.g. Trashcan
* e.g. Crazyflie

* 2s

RFC  {TODO} These or these XT30

* 3s - 6s

Battery for 3 to 6 S connectors: XT60 more amps then 2x XT60 side by side ;)

Why: Less time spend on So they can be used without conversion Soldered everywhere over time

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

If using an R-XSR the Firmware MUST be [v190311 EU LBT](https://github.com/tudelft/tx_configs/raw/master/taranis_x9dp_se/fs/FIRMWARE/R-XSR_LBT_190311.frk), reflash possible via STK module or via a Taranis X9D transmitter with specific flashing cable in the transport box.

# Data Transmission

## Wifi based on ESP8266 or build in wifi
[*MUST* use this firmware](htpp://)
## XBee Pro S1
[*MUST* use Firmware version E2](http://) 
## Herelink
[*MUST* use Firmware

## Si10xx
Modem Si10xx 868/900 based modems, So *not* the new RFD900_emp32
Connector RP-SMA female for signal out, maning antennas have a RP-SMA Male
[*MUST* use this Firmware](http://) 

## Telemetry FrSky

Whenever RX telemetry output is not needed, 99% of cases, it should be disabled in RC transceiver

# OS's

## Ubuntu 16.04.x or 18.04.x
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
# Pixracer v1.0 R14
Why: robust, versatile, available, cheap, hardfloat F4, SD card
# Lisa MXS: 
Why: Fits certain projects light small
# Parrot based boards ARDrone2, Bebop, Bebop2, Disco: 
Why: No need to build something, cheaply available
# Crazybee F4 Pro board
Why: complete, light, cheap, available, hardfloat F4. cc2500 chip usable for mesh networks

# Web technology: 
Lamp server

# CMS 
Wordpress, if need custom plug-in by student but made open to public

# Version control

* **Git** v2 or higher, and for old SVN repositories an Git SVN extensions can be used

# Basic Software 

Software used should have at least Linux,optionally Win and OSX version.
Exception are very specific programs for hardware, e,g. certain measuring equipment

* KiCad  (WXL)
* FreeCad (WXL)
* Dia (WXL)
* Xflr (WXL)
* Inkscape (WXL)
* Gimp 2.10 (WXL)
* LibreOffice (WXL)
* ? qelectrotech https://qelectrotech.org
  ? https://sourceforge.net/projects/tinycad/
* Motive v2.0(Optitrack)

# Google services
Sadly not open, but access to all your data pragmatic for the time being

# Hardware PCB/schematic designs AP

* Current From EAGLE to KiCAD wherever feasable
In some scenarios Altium v19 may be used

# RC transmitters

* Taranis X9D [Firmware XJT EU LBT and OpenTX 2.2.4.x with fixed RSSI warning]()
* Taranis X-lite [Firmware XJT EU LBT and OpenTX 2.2.4.x with fixed RSSI warning]()
* SM600: PC USB "joystick type" RC transmitter SM600
* iRangeX 4in1 Multi-module in other TXs with MAVLab firmware to be found here:

End of life:
* Devo 10 : pull the last release from https://github.com/tudelft/tx_configs