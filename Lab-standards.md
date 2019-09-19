# Lab Standards

# About

## Why

## Standardization, the issue

## How - Inventory

## What

## Benefits

The benefits of some form of standardization

## Contra Standardization

Not in all cases is a standarization wished for ...

# Procedures

* papers
* videos
* PR
* public aperance

# Materials

# Suppliers

# OS's

RFC, more can be added of specific need

* Ubuntu 16.04 64 bit
* Ubuntu 18.04 64 bit
* Ubuntu 32/64bit if embedded
* MS Win10

# Hardware

## Airframes

First to be said if you develop new contro new airfoild new thins, no need to adher to any airframe standard

But if you use the airframe to perform other control resers or vision base experiment we have

* Bebop1
* Bebop2
* Mambo
* Disco
* Trashcan
* Crazyfly

## Battery Charging

## Battery Storage

## Battery Connectors

* 1s, three different types

* {TODO} for on very light and  tiny airframes
* On e.g. Trashcan
* e.g. Crazyflie

* 2s
RFC  {TODO} These or these

* 3s - 6s

Battery for 3 to 6 S connectors: XT60 more amps then 2x XT60 side by side ;)
Why: Less time spend on So they can be used without conversion Soldered everywhere over time

# RX Receivers:

THe Lab has Standardized on FrSky RX or FrSky compatible RX

Which: R-XSR
Why: Good range, telemetry backoption, open protocol, cheap, available, open software flashable
How: Buy a bunch
What about delfly: FrSky XM cpp or Sbus these ones can replace the current deltang

Must adhere to new EU rules LBT ETSI v1.8.1
ALL receivers in the lab should be FrSky or compatible, if not the AC should get another RX

# RX behaviour

# RX Output signal
## RX indication light colors

# RX FIRMWARE

If using an R-XSR the Firmware MUST be [v190311 EU LBT](https://github.com/tudelft/tx_configs/raw/master/taranis_x9dp_se/fs/FIRMWARE/R-XSR_LBT_190311.frk), reflash possible via STK module or via a Taranis X9D transmitter with specific flashing cable in the transport box.

# Data Transmission

## Wifi based on ESP8266 or build in wifi
## XBee Pro S1
Firmware version E2?

## Si10xx

Modem Si10xx 868/900 based modems, So not the new RFD900_emp32

Connector RP-SMA female for signal out, maning antennas have a RP-SMA Male

## Telemetry FrSky

Whenever RX telemetry output is not needed, 99% of cases, it should be disabled in RC transceiver

# OS's

## Ubuntu 16.04.x or 18.04.x

## Windows

# Markup: 

**Markdown**, Github version allowed.

# Autopilots

There are just to many...so some default RFC:

# Pixhawk Clones 2.4.8 - 
Why: Versatile, Well flexible, Available cheap
# Pixracer v1.0 R14
Why: robust, versatile, available, cheap, hardfloat F4, SD card
# Lisa MXS: 
Why: Fits certain projects light small
# Parrot based AP's ARDrone2, Bebop, Bebop2, Disco: 
Why:No need to build something
# Crazybee F4 Pro
Why: complete, light, cheap, available, hardfloat F4. cc2500 chip for mesh

# Web technology: 
Lamp server

# CMS 
Wordpress, if need custom plugin by student but made open to public

# Version control

* **Git** v2 or higher, and for old SVN repos an Git SVN extentions can be used

# Basic Software 

Software used should have at least Linux,optionally Win and OSX version.
Exeption arevery specific progrems fro hardware, e,g. certain measurein equipment

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

* Devo 10 : pull the last release from https://github.com/tudelft/tx_configs
* Taranis X9D FW XJT EULBT and OpenTX 2.2.3.x fixed RSSI warning
* PC USB "fake" RC transmitter SM600
* iRangeX Multi-module