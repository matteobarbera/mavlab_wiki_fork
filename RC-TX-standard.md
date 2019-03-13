# RC TX Standard

# Lab RC Transmitter standards

# About

This document is a RFC to get a unified MAVlab atandard for RC Transmitters (RC TX)
RCF: request for COMMENT, so NOT a final document, it can be seen as in Alfa/Beta stage.

## What it is not
It is **NOT about private TX equipment**, but if this equipment is used in a MAVLab setting, then this standard must be adhered to also.

# Discussion
Things to be discussed 

## switch colors
## switch behaviour (not strickly TX related but a good opportunity)
## AETR or TAER 
## etc. etc.

# Outcome

RFC: failure minimization due to AC pilot error 

# RFC about standards

## Protocol
The over air protocol **must** be FrSky
### Exemptions
_Temporary exemptions_ An airframe that cannot have a RX swapped since it is embedded in the mainboard. In the transition period till 2020 DSMx is allowed.

Before 2020 all RX not FrSky must be exchanged.

# TX SWITCHES

## MODE
All transmitter **MUST** be mode 2

Philosophy: Roll and Pitch movement on one stick make steering with one hand possible, one hand for othert actions in case of need or emergency. Also coupling is better and for Heli more precise.

## KILL
* Safe is TOWARD YOU, so kill is TOWARDS you
Philosopy: in case of panic you arm over all contols towards you make engine stop mode manual and kill to kill position.

* Kill is https://github.com/tudelft/mavlab/wiki/RC-TX-standardAlways on the LEFT and Bottom swith, if there is no bottom switch we make one
Staring is stil possible with one hand kill non accidentally with other hand

## FLIGHTMODE
* Flight  MODE switch is AWAYS above Throttle, so since we ALWAYS fly mode 2 it is on the LEFT side
Philosopy: in case of emegency on does not ned to look only ONE hadnmovment is enough for mode change and quick throttle change

* Flight mode is ALWAYS a 3 way switch, if TX does not have a 3 way switch we MODIFY the TX to have it or do NOT use the TX

* Since "Manual is safer?" (debate) "manual(or att is towards you)"

## GEAR
* Landing gear switch is on the RIGHT side of TX

## FLAPS
* Flaps switch are on the RIGHT. A potmeter knob is allowed for flaps CCW no flap, CW full flap, on side of TX to front NO flap towards, Full flap

# COLOR CODING

RFC TX Switches color coding

RED = KILL; philosophy, red is common for danger, stop, etc
BLUE = MODESWITCH philosophy, on thr other colorspectrum than RED, less change of confusion for colorblind
YELLOW = GEAR
WHITE = FLAP

If Switches are of Potmeter type, still try to paint color on in if at all possible. Or sticker a point in the color above the potmeter

Note: **Green is NEVER used** since it implies something safe

# Specifics

If there are specific switches use the can be defined here. If it is impossible to make a standard there. The switch will be in the Preflight check but can **NOT be for essential operations**

## Multirotor

## Helicopter

## Fixedwing

## Transitional

# Power ON/OFF
It must be possible for the tranmitter to be switched on OPERATIONAL state **WITHOUT pressing ANY buttons** on the TX
Philosophy: In (autonomous)flight,  with TX off or low battery off battery swap we can keep **EYES on Aircraft** and can not make mistakes forget pressing buttons or menus items. Sme for on ground switch on, when **ON the TX MUST be 100% operational**

The off position of the TX is TOWARDS the Pilot. 

NOTE: Some TX do not have a real on/off. Those TX should NOT be used in the Lab for flight operations.

# TX HARDWARE

All TX should be X9D SE, with a very very good reason not to have that TX.

# FIRMWARE
ALL firmware on TX should have a **standardized proved pre-build version** with defined compiler and defined libraries.

If TX firmware should be upgraded, a SERIOUS test program is a must and only after proven and done all test new firmware can be introduced in use in the field ops. 

# TX settings

TX setting will be unified in the TX so the output is the same for ALL transmitters

# PC JOYSTICKS
Flight with non separated TX e.g. over data-link is NOT allowed for ROC operations, for ROC-light is should be discussed.

# TX DISPLAY
All TX displays should be monochrome full sun lit readable and readable in the dark

# TX WARNINGS
RFC t.b.d.

# Language

The language of the TX and if use speech should be **ENGLISH only**

# BEHAVIOUR of CONTROLD and SWITCHES

[A page RFC on standard TX behaviour can be found here](RC-TX-control-and-switch-behaviour-standard)
##THROTTLE
###Electric engine
###Gas engine

##ROLL

##PITCH

## YAW
## MODE

## KILL
## GEAR
## FLAP
## AUX1234