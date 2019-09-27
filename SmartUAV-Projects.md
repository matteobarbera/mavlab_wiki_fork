SmartUAV project page with descriptions

SmartUAV bundles functionality into projects, these include 3rd party libraries and API's used by SmartUAV. These projects are listed below


||=Project =||=Name =||=Version =||=Description =||
|| ARDrone || || Internal || ||
|| BehaviourTree || || Internal || ||
|| DWAV || Delft Workspace for Artificial Vision || Internal || Artificial Vision Module Library ||
|| FDC || Flexible Data Channels Library || Internal || Seamless OS and hardware interfacing ||
|| GLUT || Open source Graphics Library Utility || freeglut 3.7 || 3D graphics base library ||
|| FLTK || Fast Light Toolkit || 1.3.3 ||  Graphical User Interface library ||
|| FLU || FLTK Utility Widgets || 2.14 ||  Additional libraries for drawing in FLTK ||
|| MavLink || || External || ||
|| ModuleEditor || Module Interconnection and settings Editor || Internal  || Connect displays, drivers, sensors, etc... ||
|| NavDisplays || || Internal || ||
|| OpenCV || Open source Computer Vision || 2.4.9 || Computer Vision Base Library ||
|| Paparazzi || || External || ||
|| PLIB || Portable Gaming Library || 1.8.4 || libraries for rendering, 3D, fonts, network, joystick, AC3D import ||
|| Quadrotor || || Internal || ||
|| SmartUAV || || Internal || ||
|| SDL || Simple Direct Media Library || 1.2.9 || ||
|| StdUtils || || Internal || ||
|| tinyxml || Load/Write XML || 2.6.2 || Logging/Saving xml files ||



=== ARDrone ===
=== BehaviourTree ===
Project to develop Behaviour trees with UAVs
=== DWAV ===
Contains all user designed modules to be used in Capabilities
=== FDC ===
=== GLUT ===
This provides libraries to simplify drawing in OpenGL
=== FLTK ===
FLTK is used as the main window manager and OpenGL interface for drawing windows and their content.
=== FLU ===
This is used to add widget functionality to FLTK. We use it primarily to draw the tree browsers and the Capability graphs in the main Editor window.
=== MavLink ===
=== ModuleEditor ===
This library contains the functions to draw the Editor window. It handles all Editor window events. At runtime, it auto-generates all modules in the Capability tabs and connects all the inputs and outputs of each module.
=== NavDisplays ===
=== OpenCV ===
=== Paparazzi ===
=== PLIB ===
This is used primarily to compute the location of a camera in a simulated environment scene and to generate the rendered image from that perspective.
=== Quadrotor ===
=== SmartUAV ===
This contains all the main libraries for backend SmartUAV. It is made up of the following sub-libraries:
{{{
libAFMS - Aircraft Flight Management Systems: GUIs for UAV control
libComm - Communication: Libraries for all communication interfaces
libFcs  - Flight Control Systems: AHRS, device drivers...
libGcs  - Ground Control Process: Manage data links and offer data to interfaces
libSim  - Simulation: Libraries control main sim windows, simulation update, environmental simulation...
Media   - Contains all user specified simulation and environmental settings
}}}
=== SDL ===
We use this to get Joystick inputs.
=== StdUtils ===
These libraries provide the functions needed to run SmartUAV. The main FLTK loop is found here as well as cross-platform code to provide accurate time to SmartUAV.
=== tinyxml ===