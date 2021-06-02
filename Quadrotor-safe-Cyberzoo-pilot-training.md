# Safe-Zoo ( Pilot Training )

The aim of the project "safe-zoo" is to facilitate and accelerate the learning process of novel drone pilots. All code can be found in the official tudelft paparazzi git under the branch "cyber_zoo_train". The code has been tested for both a Bebop and Bebop2 in the cyber-zoo.
## General Description of the project
The general idea behind "safe-zoo" is to use a specifically designed flight-plan to allow novel pilots under safe conditions to manually control a given drone (e.g. Bebop2) in the faculty's cyber-zoo. In contraddiction, when an unsafe situation occurs, the autopilot is commanded to take control and reastablish safety.
### Controller mode:
The flight plan makes use of the controller mode "Auto2" which can be coded to different control profiles based on defined exeptions. More precisely, the idea is to set the control profile to "ATT" (e.g. manual control) in safe conditions and in "NAV" (e.g. autopilot) in unsafe conditions. 
### Safety conditions:
A safe operational space is established through soft geofencing in the flight-plan file. This is a rectangular box of a selected height (default 2.2 m) and defined by the reference points P1 to P4, roughly corresponding to the green area of the cyber-zoo. These reference points can be changed by the user in the flight plan to tune the pilot's freedom and flight experience. 
### Description of the mission 
When the drone is flying inside of the geofenced area, the controller mode "Auto2" is set to manual control. This means that the pilot is in charge of maintaining the wanted attitude and pace of the drone. When the drone exits the geofenced area, generating a safety hazard for both the operator and the drone, the control mode is automatically switched to the autopilot profile. This means that the stabilization routine will immediately start ensuring that the drone will not crash. Later, the drone will be redirected by the autopilot to the "Standby" waypoint where a flare and landing procedure is performed. Once the drone has landed, the control mode is automatically switched again to manual and the pilot can resume the training. \
**IMPORTANT:** The pilot is advised to kill throttle as soon as the autopilot takes over so to avoid unexpected take-off when the manual control profile is reastablished.  
## Step by step guide to initialisation
1. Initialize paparazzi
2. Make sure that the selected airframe does not have a throttle limiter selected. This means that the following line should be present and uncommented in the autopilot block " define name="NO_RC_THRUST_LIMIT" value="TRUE" ". Of course make sure to include the snippet with the correct C syntax.
3. Select as flight plan " flight_plans/tudelft/train_safe_zoo.xml"
4. Make sure that a suitable controller is connected to your ground station (e.g. sm600) and is well calibrated. Further information can be found in the paparazzi crash course pdf. 
5. Make sure that the drone has at least three reflective stickers in a non simmetrical pattern and that the optitrack system is connected to the ground station and is detecting the drone. Safe the detected pattern as a rigid body and write down thee streaming ID.
6. Select "ap" and flash the drone. 
7. Execute a session "Flight UDP Optitrack + Joystick"
8. Change the Joystick setting string to select the correct controller xml file (e.g. "sm600.xml" instead of "hobbyking.xml")
9. Change the NatNet setting string such to correctly specify the streaming ID and the aircraft ID. For example, with streaming ID=1 and aircraft ID=48, the string should end with "-ac 1 48"
10. Check that the ground station has a 3D fix and that the controller is being detected
11. On your controller engage the "Auto2" mode.
12. From the flight plan select and execute the block "Sbinnala". The drone can now be manually controlled
13. Enjoy and Safe training! 