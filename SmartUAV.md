# SmartUAV

# About

SmartUAV is a UAV simulation platform developed by the MAVLab to investigate Many aspects of UAV implementation. It provides a framework to do research into all areas of UAV development ranging from advanced Graphical User Interfaces (GUIs) to investigate Human Machine Interaction (HMI) to novel vision based control and guidance algorithms. Being designed and maintained in-house, SmartUAV can be altered and updated as the user requires.

SmartUAV is built as a modular plug and play system, where the programmer can choose which modules are included and build the simulation as required. This wiki page will try to provide you with all the information you need to master the SmartUAV simulation platform.

# Getting Started

## Installation
SmartUAV is cross-platform and has been extensively tested on Window 7 and Linux. Information on how to get the most recent version of SmartUAV and compile on your local machine can be found at [Instalation](SmartUAV-Installation)

## Projects
As mentioned earlier, SmartUAV has a modular structure which is broken up into what we call Projects. The list of projects with detailed descriptions of each project can be found here: [List of Projects](SmartUAV-Projects)

## Quickinstall

The ultra short intro is:

**Linux:**

```
svn checkout https://svn.lr.tudelft.nl/MAVLAB/SmartUAV/
cd SmartUAV/Software
make`
cd SmartUAV
../bin/SmartUAV
```

**Windows:**

```
tortoisesvn -> checkout doen
cmake installeren en SmartUAV/Software map selecteren als source en SmartUAV/Software/build als target
cmake -> configure -> generate (Default settings)
visual studio (express) 2012 (later kan ook maar meer warnings) open de SmartUAV.sln uit de SmartUAV/Software/build map
change the debug path setting to run from ./SmartUAV/Software/SmartUAV/

```



