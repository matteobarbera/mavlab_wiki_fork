# Simulation
Chances are, at some time during your time at the MAVLab, you want to simulate soft- or hardware. There are some great reasons to do so:
- You can get rid of all bugs in the code before moving to the real hardware
- If something doesn't work as intended, no hardware is broken
- You don't need to run to your testing area every time you make a small change to your code
- You can test performance in extreme or dangerous situation, that are not possible/safe to be reproduced in reality

*Keep in mind: What doesn't work in simulation won't work in reality, but just because it works in simulation, doesn't mean it will work in reality!*

In the following, you can find an overview of simulation environments that are/have been used by people at the MAVLab. This list is meant to help you choose the environment that works best for what you want to do, but don't be afraid to try out something new if you don't find what you're looking for - However, be sure to add it to the list if it works, so other may profit from your experience!

## Gazebo
Several possibilities for simulating with Gazebo exist, that are covered in detail below. Gazebo is quite popular in its different implementations because there is a lot of documentation available and it is quite easy to set up. The main drawbacks are the poor graphics and the simulation speed, which can be quite slow for larger models or environments.

#### Gazebo with Hector
*Language:* C++

*Models:* [Generic Quadrotor](http://wiki.ros.org/hector_quadrotor)

*Description:* 

#### Gazebo with Paparazzi

#### Gazebo with PX4

## FlightGoggles

## MATLAB / Simulink

## Airsim

## Others
The simulation environments listed here have only been used for very specific purposes and there might not be a lot of know-how around on how to use them.

#### ARGoS

#### unrealCV

#### Swarmulator