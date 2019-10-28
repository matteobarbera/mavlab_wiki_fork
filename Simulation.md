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
*Language:* C

*Models:* [Many](https://github.com/tudelft/paparazzi/tree/master/conf/airframes/tudelft)

*Description:* Paparazzi offers a simulating environment which can use the gazebo simulator. The advantage of this is, that you can use exactly the same code in the simulation as you do with the real drone (if the real drone uses paparazzi). This environment can also be used for vision-in-the-loop (low-end graphics). Right now there are however a few bugs with low level AHRS/INS, and the simulator doesn't allow multi-agent simulations.

#### Gazebo with PX4

## FlightGoggles
*Language:* C++, Unity 3D, ROS

*Models:* Generic Quadrotor

*Description:* FlightGoggles is a Unity based, highly vision focused simulator. It has mainly been used for drone racing, but can be a good choice wherever high quality graphics are needed for testing vision based navigation. This simulator however requires a good graphic card to run properly and the simulated environment is difficult to modify. Self-developed code is implemented through ROS. Last update to the github repo was in May 2019, so the simulator might not be maintained anymore.

## MATLAB / Simulink
*Language:* MATLAB

*Models:* [Beebop 2](https://bitbucket.org/SihaoSun/bebop2_aerodynamic_model/src/master/)

*Description:* Matlab/Simulink is a very accessible environment to do quick tests, but also to develop more sophisticated models. While it offers no graphical simulation capacities, it is really good to achieve high physical accuracy and allows the user a high flexibility in his implementations.

## Airsim
*Language:* C++, Python, C#, Java

*Models:* 

*Description:* Open-source simulator developed and maintained by Microsoft, built on Unreal Engine (Unity release also available). Focused on computer vision and AI, therefore computationally expensive to run

## Others
The simulation environments listed here have only been used for very specific purposes and there might not be a lot of know-how around on how to use them.

#### ARGoS
Large-scale multi-agent simulator.

#### unrealCV
Plugin to get high quality visuals from an Unreal Engine scene. Dynamics must be programmed independently and capturing images can take quite long.

#### Swarmulator
Lightweight C++ simulator for swarms, written by Mario for his research and thus not actively maintained.