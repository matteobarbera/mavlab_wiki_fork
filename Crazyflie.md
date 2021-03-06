# Getting started

## Resources

- [Assembling your Crazyflie](https://www.bitcraze.io/documentation/tutorials/getting-started-with-crazyflie-2-x/)
- [Firmware documentation](https://www.bitcraze.io/documentation/repository/crazyflie-firmware/master/building-and-flashing/build_instructions/)
- [Docs for other repos](https://www.bitcraze.io/documentation/repository/)
- [Wiki](https://wiki.bitcraze.io/) (is being replaced by the documentation above, but still holds some additional information)
- [Forum](https://forum.bitcraze.io/) (probably the most valuable source of information!)

# Cyberzoo flight

To fly in the Cyberzoo, you can use the suite developed [here](https://github.com/Huizerd/crazyflie-suite). It allows flying with OptiTrack or ultra-wideband (UWB) nodes.

## OptiTrack

The Crazyflie suite contains a NatNet client to connect with the OptiTrack system. You can verify that your computer is receiving data using the `optitrack_test.py` file. If no data is received, try turning off your WiFi and firewall (often `sudo ufw disable`). The bumper that can be printed using the file below can be used to attach IR markers. Decent OptiTrack settings seem to be 120 fps, 250 exposure, 200 threshold and 15 led.

## UWB

The Loco Positioning System allows for absolute position measurements using UWB anchors. These can be placed on the stands in the corners of the Cyberzoo (at least 2 powerbanks + 4 micro-USB cables needed). Additional stands can be printed using the file below (from Bitcraze). 4 anchors should suffice for both TWR and TDoA positioning, given that you have a Z-ranger or Flowdeck to measure altitude. TWR is more accurate than TDoA, but is limited in number of Crazyflies and anchors. If you find that you lose connection to the anchors often, you can increase transmission power on both the [Crazyflie](https://github.com/Huizerd/crazyflie-firmware/commit/7a58e22ef5ff9639d4da4cca5124dc580a81fd3e) and [anchors](https://github.com/Huizerd/lps-node-firmware/commit/d0b0cf4ba55f5745800bfa89d78a8dc632351d62) (not for production), or switch to a 'long range' mode for TDoA ([Cf](https://github.com/Huizerd/crazyflie-firmware/commit/fde675024335a303b2ba37e0f28221f75bbfceae), [anchors](https://github.com/Huizerd/lps-node-firmware/commit/cfbfd13dcf729dc46cc97e741ba5b0523223b825)). The anchor stands in the Cyberzoo all have a number. If you match the IDs of each anchor with these numbers, you can write the following locations to your anchors through the client, and save yourself the trouble of having to measure up the Cyberzoo:
```
# Cyberzoo LPS position file
# Positive X: to the right
# Positive Y: to the back
# Positive Z: upwards
# CCW order
# Closest to table
0:
  x: -4.53
  y: -4.62
  z: 1.69
# No power outlet
1:
  x: 4.63
  y: -4.81
  z: 1.57
# Furthest corner
2:
  x: 4.72
  y: 4.88
  z: 0.87
# With power outlet
3:
  x: -4.70
  y: 4.60
  z: 1.72
```

# 3D printer files

- [Bumper](../raw/master/print_files/UM3_cf_bumper.gcode)
- [LPS anchor stand](../raw/master/print_files/anchor-stand.stl)

# Custom decks/boards

TBA
