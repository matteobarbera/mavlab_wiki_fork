# DelFly Assembly

  1. [motor-gear assembly](https://github.com/tudelft/mavlab/blob/master/pdf/delfly/A-motorGearAssembly.pdf)
  2. [wings](https://github.com/tudelft/mavlab/blob/master/pdf/delfly/B-wingConstruction.pdf)
  3. [tail](https://github.com/tudelft/mavlab/blob/master/pdf/delfly/C-tailConstruction.pdf)


 -  The old instructions using previous wing construction method are available [here](https://github.com/tudelft/mavlab/blob/master/pdf/delfly/delfly.assembly.2014.pdf)


# Parts

## Carbon

 - You can buy carbon rods at http://www.dpp-pultrusion.com/
 - or http://www.carbonwinkel.nl/nl/carbon-producten/900-vec-staaf-vinylester-carbon.html

## Motors

[1.5g Mighty Midget](http://microbrushless.com/products/micro-uav-propulsion/1-5gm-mighty-midget-motors/), we use a **custom design**!!!

Order by sending an email to Mr. Chandrashekhar (sales@microbrushless.com), say it is the DelFly version and specify the number of windings. The following table can serve as a guideline:

| number of turns | DelFly type |
| --- | --- |
| 18-19 | Quadthopter a.k.a. Flappy (probably...) |
| 22-25 | DelFly Transformer |
| 28 | Heavy smart Delflies - Explorer / DelFly II with additional sensors |
| 30+ | Lightweight Delflies |

# Motor controllers (ESCs)

- Supermicro MX-3A or MI-3A, e.g. from [Hobbyking](http://www.hobbyking.com/hobbyking/store/__44697__SuperMicro_Systems_Brushless_ESC_3A_Mi_3A.html)

- The ESCs need to be flashed with BLHeli software: [[tutorials-flashBLHeli]]

# Receiver + servos

## Receiver:

 - [Deltang Rx31, SumPPM version](http://www.deltang.co.uk/rx31b.htm)

## Servos:

- Light (but weak and hard to get, used on Explorers): [Sub  Micro  .50 gm.  LZ    SERVO](http://microflierradio.com/UltraSubMicroServos.html)  

- Linear servos: 2.4ghz SuperMicro Systems - Single Linear Servo

- Strong rotary servos (tail-less designs): [HK 5330](https://hobbyking.com/en_us/hobbykingtm-hk-5330-ultra-micro-digital-servo-0-17kg-0-04sec-1-9g.html?___store=en_us)

## A receiver & servos combo-board

Can be used for "stupid" Delflies:

 -[Supermicro with brushless ESC](http://www.hobbyking.com/hobbyking/store/__56166__2_4Ghz_SuperMicro_Systems_DSM2_Compatible_Receiver_w_Brushless_ESC_Linear_Servos.html)

- Instructions for [turning gyro autostabilization off](https://svn.lr.tudelft.nl/trac/MAVLAB/attachment/wiki/delflyEquipment/Turning_stabilization_off.txt)
- [Programming instructions](http://www.hobbyking.com/hobbyking/store/uploads/454997728X86361X35.pdf)
- [MD-RX62H Flashing BLHeli](https://svn.lr.tudelft.nl/trac/MAVLAB/wiki/electronics/MDRX62H)

## Supermicro with brushed 
 
 -ESC(http://www.hobbyking.com/hobbyking/store/__56167__2_4Ghz_SuperMicro_Systems_DSM2_Compatible_Receiver_w_Brushed_ESC_Linear_Servos.html)

- [Programming instructions](http://www.hobbyking.com/hobbyking/store/uploads/213817245X103718X6.pdf)


# Autopilot boards

 - [Lisa/S](https://1bitsquared.com/products/lisa-s)  (discontinued)

 - Lisa/S v2 (under development)

 - [Lisa MX S](https://wiki.paparazziuav.org/wiki/Lisa/MXS_v1.0) - ask Christophe if you need one

 - MilFly project: https://svn.lr.tudelft.nl/MAVLAB/Electronics\DelFly_03_MilFly_v2

# Wifi modules

- ESP 8266 ESP 09, code and flashing instructions [here](https://github.com/paparazzi/esp8266_udp_firmware/tree/master)

# Cameras & Video Transmitters

 - [FPVHobby](http://www.fpvhobby.com/)

# Lenses

 - [MISUMI](http://www.misumi.com.tw/)

 - Type: l2125ar-M5.5
