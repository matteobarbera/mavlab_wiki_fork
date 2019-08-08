# Basic information

* Dimensions: ??x??x??
* Axis: X, Y, Z
* Software: XpertMill?
* Supported file formats: ??? 

The Step Four Mill can be used both with the XpertMill? controllers, as well as the LinuxCNC controller. Please see the following PDF for how to connect the cables to switch between the two.

https://svn.lr.tudelft.nl/trac/MAVLAB/attachment/wiki/machinery/cnc3axis/HOW%20TO%20SWITCH%20Step%20Four%20Mill%20CABLES.pdf
Before Milling

1. Check that bit is correctly fitted in chuck.
1. Check that spindle is correctly fitted to machine.
1. Check that spindle can be activated by turning off safety located on side of mountable piece.
1. Set zero point using yellow cursor.
1. Affix vacuum hose to spindle, and activate vacuum.
1. Put on appropriate safety gear.
1. Run simulation of milling your part to verify tool-path. 

# XpertMill

## Setting the Zero Point

1. Click on yellow 'Set Zero Point' icon in upper left of screen.
1. Position mill such that the bit rests just barely (sheet of paper) above workpiece.
1. Click arrows next to coordinate positions.
1. All OK to accept new zero point. 

## Milling Your Part

1. Ensure image on computer matches with material on tray.
1. Define contours.
1. Define start points and directions.
1. Define layers.
1. Define milling order; mill from inside to out. 

##Defining Layers

Upon drawing in Xpert Mill, your drawings will be assigned to layers.
Layers can be used to add material information to the program and tell it how to mill the part.
Click on Layers tab at bottom of window.
Double click on the layer you wish to edit.
Input material information (thickness, type of material).
Input desired depth of cut for that layer.
    Different layers can be used to achieve cuts at different depths. 
Increase number of mortices. The more mortices, the less material removed with each pass of the mill, the less likelihood of breaking a bit.
    Note: Increasing mortices also increases necessary mill time and heat in the material. 
Input feed information.
    Spindle speed cannot be defined in the program, and must be changed manually on the spindle. 
Input tool information.
    Note: If current tool does not match tool defined for that layer the program will display an error message. If the currently defined tool is incorrect, press update. If the layer requires a different tool, click 'Yes' and the spindle will move to the tool change point. Remember to disconnect power to mill before anything else when changing tools. 
You can change which layer an object is in by opening up the 'Object Properties' window and toggling the layer button. Assigning an object to a layer that does not exist will create a new blank layer. 

## Creating Pockets

1. Select define contours tool.
1. Select contour you wish to make into a pocket.
1. Define as inner contour.
1. In contour selection menu find Broaching submenu.
1. Select "Broach Line Parallel to Contour."
1. Run milling simulation to ensure correct area is milled. 

# Information on mill settings like feed rate, RPM, materials

​http://zero-divide.net/?page=fswizard&shell_id=199&lang=en

# Helpful Links

​https://www.youtube.com/watch?v=m31qk1UdrbQ
