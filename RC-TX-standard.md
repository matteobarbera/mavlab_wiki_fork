# RC TX Standard

# Lab RC Transmitter standards

## What it is not
**If private TX equipment**, is used in a MAVLab setting, then this standard must be adhered to also.

# Outcome

RFC: failure minimization due to AC pilot error 

# RFC about standards

## Protocol

There is only one protocol in use in the lab and that is **FrSky D16**. 

TIP: If you still use old equipment ask you lab contact for a replacement receiver and Transmitter

###EOL

 - Crossfire (only very rare ocasion/airframes)
 - FASST (deprecated)
 - DSMX (deprecated)
 - DSM2 (very deprecated)

# TX SWITCHES

## MODE
All transmitter **MUST** be mode 2

Philosophy: Roll and Pitch movement on one stick make steering with one hand possible, one hand for other actions in case of need or emergency. Also, coupling is better and for Heli more precise.

## KILL
* Safe is TOWARD YOU, so kill is TOWARDS you

* Kill is https://github.com/tudelft/mavlab/wiki/RC-TX-standard always on the LEFT and Bottom switch. If there is no bottom switch we make one

## FLIGHTMODE

* Flight  MODE switch is AWAYS above the pitch stick, so since we ALWAYS fly mode 2 it is on the RIGHT side
Philosophy: when changing modes changes in throttle are often also needed and doing 2 things with one hand is harder.

* Flight mode is ALWAYS a 3 way switch if TX does not have a 3 way switch we MODIFY the TX to have it or do NOT use the TX

* "manual or attitude mode is when you (the pilot) is flying, then you place the switch towards you"

## GEAR
* Landing gear switch is on the RIGHT side of TX

## FLAPS
* Flaps switch are on the RIGHT. A potmeter knob is allowed for flaps CCW no flap, CW full flap, on side of TX to front NO flap towards, Full flap

# COLOR CODING

RC_transmitter_FrSky_Taranis_X9DplusSE_standarized_switches_800x_01.jpg

TX Switches color coding

RED = KILL; philosophy, red is common for danger, stop, etc
BLUE = MODE SWITCH philosophy, on other colorspectrum than RED, less change of confusion for colorblind
YELLOW = GEAR
WHITE = FLAP

If Switches are of Potmeter type, still try to paint color on in if at all possible. Or sticker a point in the color above the potmeter

Note: **Green is NEVER used** since it implies something safe

## ALL

### Dual rate

ORANGE = Dual rate on top left next to mode

Philosophy: Sometimes one does not know the control effectiveness at a higher or slower speed. To be able to give more or less authority a switch can be assigned as a so-called "Dual-Rate" switch. next to mode since often neede when switching to manual mode pull back 2 at the same time.

### Drop/cam or other triggers

CLICK = PURPLE on the right side
Philosophy: Sometimes one wants to perform a on time pulse action like take picture, drop store, tupple etc.
For this, the CLICK switch is used

## Transitional

### Forward/Hover toggle

# Power ON/OFF
It must be possible for the transmitter to be switched on OPERATIONAL state **WITHOUT pressing ANY buttons** on the TX
Philosophy: In (autonomous)flight,  with TX off or low battery off battery swap we can keep **EYES on Aircraft** and can not make mistakes forget pressing buttons or menus items. Sme for on ground switch on, when **ON the TX MUST be 100% operational**

The off position of the TX is TOWARDS the Pilot. 

NOTE: Some TX do not have a real on/off. Those TX should NOT be used in the Lab for flight operations.

# TX HARDWARE

All TX should be X9D SE, with a very very good reason not to have that TX.

# FIRMWARE

ALL firmware on TX should have a **standardized proved pre-build version** with defined compiler and defined libraries.

If TX firmware should be upgraded, a SERIOUS test program is a must and only after proven and done all test new firmware can be introduced in use in the field ops.

The firmware should adhere to ETSI EN 300 328 v1.8.1 so for FrSky EU LBT. EULBT based firmware is allowed in other parts of the world, other way around is not.

[One must get the correct firmware **only from here**](https://github.com/tudelft/tx_configs)

# TX settings

TX setting will be unified in the TX so the output is the same for ALL transmitters

See https://github.com/tudelft/tx_configs

# PC JOYSTICKS

Flight with non separated TX e.g. over data-link is NOT allowed for ROC operations, for ROC-light is should be discussed. [Settings to be found here](https://github.com/tudelft/tx_configs/sm_600)

# TX DISPLAY
All TX displays should be monochrome full sun lit readable and readable in the dark

# TX WARNINGS
RFC t.b.d.

# Language

The language of the TX and if use speech should be **ENGLISH only**

# BEHAVIOUR of CONTROLS and SWITCHES

[A page RFC on standard TX behaviour can be found here](RC-TX-control-and-switch-behaviour-standard)
