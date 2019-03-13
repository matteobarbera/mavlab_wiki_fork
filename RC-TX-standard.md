# RC TX Standard

# Lab RC Transmitter standards

# About

This document is a RFC to get a unified MAVlab atandard for RC Transmitters (RC TX)
RCF: request for COMMENT, so NOT a final document, it can be seen as in Alfa/Beta stage.

# Discussion
Lots of things need to be discussed e.g. colors, behaviour, AETR or TAER etc. etc.

# Outcome

RFC: AC pilot flight operations failure minimalization

# RFC about standards

## Protocol
The over air protocol **must** be FrSky
### Exemptions
_Temporary exemptions_ An airframe that cannot have a RX swapped since it is embedded in the mainboard. In the transition period till 2020 DSMx is allowed

# TX SWITCHES

## MODE
All transmitter **MUST** be mode 2

Philosophy: Roll and Pitch movement on one stick make steering with one hand possible, one hand for othert actions in case of need or emergency. Also coupling is better and for Heli more precise.

## KILL
* Safe is TOWARD YOU, so kill is TOWARDS you
Philosopy: in case of panic you arm over all contols towards you make engine stop mode manual and kill to kill position.
On the right side to extend the flaps en exten the landing gear

* Kill is Always on the LEFT and Bottom swith, if there is no bottom switch we make one
Staring is stil possible with one hand kill non accidentally with other hand

## FLIGHTMODE
* Flight  MODE switch is AWAYS above Throttle, so since we ALWAYS fly mode 2 it is on the LEFT side
Philosopy: in case of emegency on does not ned to look only ONE hadnmovment is enough for mode change and quick throttle change

* Flight mode is ALWAYS a 3 way switch, if TX does not have a 3 way switch we MODIFY the TX to have it or do NOT use the TX

* Since "Manual is safer?" (debate) "manual(or att is towards you)"

## GEAR
* Landing gear switch is on the RIGHT side of TX

## FLAPS
* Flaps switch are on the RIGHT, a potmeter is allowed for flaps CCW no flap, CW full flap, on side of TX to front NO flap towards, Full flap

# COLOR CODING

RFC TX Switches color coding

RED = KILL; philosophy, red is common for danger, stop, etc
BLUE = MODESWITCH philosophy, on thr other colorspectrum than RED, less change of confusion for colorblind
YELLOW = GEAR
WHITE = FLAP, if not a

green is NEVER used since it implies something safe

# Specifics

## Multirotor
## Helicopter
## Fixedwing
## Transitional

# ON OFF
It must be possible for the tranmitter to be switched on OPERATIONAL state WITHOU pressing ANY buttons on the TX
Philosophy: in Auto flight with TX of or low battery ofd battery swap we can keep EYES on AC and cannon make istakes

The of position of the TX is TOWARDS the Pilot. Some TX do not have a Real on of. Those TX should NOT be used in the Lab for serios flight ops.

# TX HARDWARE
All TX should be X9D SE, with a very very good reason not to have that.

# FIRMWARE
ALL firmware on TX should have a standardized proved pre-build version with defined compiler and defined libraries.
If TX firmware should be upgraded, s SERIOUS test program is a must and only after proven and done all test new firmware can be introduced in use in the field ops

# PC JOYSTICKS
Flight with non separated TX e.g. over data-link is NOT allowed for ROC operations, for ROC-light is should be discussed.

# TX DISPLAY
All TX displays should be monochrome full sun lit readable and readable in the dark

# TX WARNINGS
RFC t.b.d.

# BEHAVIOUR of SWITCHES

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