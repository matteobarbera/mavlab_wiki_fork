# About

The Cyberzoo is an indoor arena where we perform our tests. It is equipped with a motion tracking system so that we may also record ground-truth data for validation. After reading this page you should be able to use the CyberZoo and perform flights, do measurements, read log files, interface with MATLAB, etc.

'''NOTE:''' this page already assumes you installed Paparazzi, which is the software we generally use to fly the drones. If you haven't done so already, then read [[paparazzi|here]].

# Getting started with Optitrack

[[http://optitrack.com/|Optitrack]] is the motion tracking system installed in the Cyberzoo, consisting of a set of ceiling mounted cameras. The cameras use reflector markers that you may stick on an object, giving you a full 3D-position measure.

'''MOTIVE''' is the software that interfaces with Optitrack. This runs on the main Cyberzoo computer. MOTIVE interfaces with the Optitrack system and afterwards broadcasts 3D-fix data over the LAN cables. You may hook these up to your computer in order to receive the data. For more information on this, see [[#Natnet2ivy||Natnet2ivy]].

The following video can help you get up-and-started, using an ARDrone 2.0 as an example: [[https://www.youtube.com/watch?v=7t6oqgIWGMc|ARDrone2 in Optitrack]]

## Optitrack Calibration for the Cyberzoo
From time to time, it is necessary to recalibrate the Cyberzoo. This will help make sure that everything is working properly and that the 3D-position data is correct.

If you have never done this before, then it is best to get someone who knows how to do it to help you through it quickly. Either way, it is best to be with two people, so that one of you can walk around the Cyberzoo to get calibration data points while the other can check the calibration status.

General step-by-step instructions on how to calibrate the Cyberzoo can be found at: [[http://wiki.optitrack.com/index.php?title=Calibration]].

'''IMPORTANT:''': The last step in the calibration requires placing a frame on the ground in order to define the [0,0] point of the Cyberzoo, as well as where the axis point to. Notice that in the middle of the Cyberzoo, there is a large black-arrow on the ground pointing towards the right. '''The convention in our Cyberzoo is that the longer end of the frame is placed along this arrow, please stick to this convention when calibrating the Cyberzoo'''.

To verify if the Cyberzoo is correctly calibrated, you can (and should!) check the following:
* The markers are visible within MOTIVE (no blinking spots in the Optitrack software)
* The position of the markers is correct

Prior to flying, from within Paparazzi's Ground Control Station (GCS) you should check that:
• '''The position of your drone in the arena is correct''', and if you manually move the drone this position changes.
• '''The heading of your drone is correct''': point your drone in different directions and verify the drone is looking in the right direction on your ground station (if not: did you calibrate the rigid body in optitrack with the nose pointing in the direction of the arrow?).
• '''The positions of your waypoints are correct'''': walk with your drone to the waypoints in your flight plan and verify that they are inside the arena (not too close to the nets) and safely reachable for the drone.

## Creating an object in MOTIVE
When your drone is in the arena, you should see the reflectors as orange points within MOTIVE. You can select them, right click, and create an object. This object will have a parameter known as User Data, which is the ID of the object. Note down what this is since you will need it later.

## Getting Optitrack live 3D-position data on your laptop with Netnet2ivy

### Natnet2ivy
Paparazzi relies on an application called natnet2ivy in order to interface with Optitrack. 
Natnet2ivy receives aircraft position information through the Optitrack system NatNet UDP stream and forwards it to the ivy bus. An aircraft with the GPS subsystem "datalink" is then able to parse the GPS position and use it to navigate inside the Optitrack system. Essentially, Optitrack will replace GPS.

You can run NatNet from within Paparazzi by selecting tools->NatNet.
You have to make sure that natnet2ivy has correct arguments that tell it the MOTIVE User Data ID for the object as well as the Paparazzi Aircraft ID (top left on the paparazzi screen)
For example, for a drone with MOTIVE ID 1 and Paparazzi ID 2, the following will work.
{{{
#!div style="font-size: 80%"
  {{{#!sh
$PAPARAZZI_HOME/sw/ground_segment/misc/natnet2ivy  -small  -tf 10 -ac 1 2
  }}}
}}}


# Frequently Asked Questions and Issues
* ''' The LAN Cable is connected to my laptop, I created an object in MOTIVE, and I am using Natnet2ivy with the correct ID, but I still have no 3D fix '''

 In this case, make sure that MOTIVE is broadcasting the data. See the [[http://wiki.optitrack.com/index.php?title=Data_Streaming_Pane|Data Streaming Pane instruction page]] and the [[http://wiki.optitrack.com/images/2/2d/Stream_StreamingPane.png|picture within]]. Make sure that 1. Broadcast Frame Data (at top) is checked and 2. "Stream Rigid Bodies" is set to true.

* '''Cyberzoo seems/is calibrated, yet the reflectors within MOTIVE still seem to flicker. Why?'''

Possible reasons are:
      1. The current exposure of the Optitrack cameras is low. Increasing this may help with seeing the markers.
      2. Your markers are too small or not well attached.

* '''I cannot change the User Data number for the object I created '''.

  This is a current bug within MOTIVE. You just have to use the value that MOTIVE creates when using the object.

# Your first test flight

# Looking at log data

# Matlab

The data recorded in the Motive software (exported as csv files with default options, i.e. quaternions are used for attitude and individual markers are also exported) can be loaded to Matlab using the following script:
https://github.com/matejkarasek/OptiTrack_CSV_import

# Recording video via the IP cameras 

## IP-cameras

The CyberZoo is equipped with two wide angle IP cameras [[http://www.grandstream.com/sites/default/files/Resources/GXV3610_V2_QIG.pdf || Grandstream GXV3610]]. Both cameras cover the whole tracking volume; one is located at the top center of the arena and one its corner. Their stream can be displayed and recorded e.g. using VLC by opening the following addresses:

* IP Camera Corner: rtsp://192.168.209.168/0
* IP Camera Top: rtsp://192.168.209.169/0

To record a stream in VLC, open Media --> Open Network Stream, enter the URL (see above), click on the small triangle next to Play and select Convert. Create a new profile (button on the right) with  the following settings:

* Profile Name -> **RAW stream** that has Encapsulation MP4/MOV
** Video codec -> tick _Video_ + _Keep original video track_

Select the created or default profile, select the destination file and click start. You will not see the video, but it is being recorded in the background. Stop the recording by pressing the stop button in VLC. This will record the stream as is, without re-encoding, and thus it does not require much CPU power. If you want to record both cameras, do the same for the second camera in a new VLC window.

Of course, you can also do all this from the command line, feel free to share the commands here :)

# Links

* Add your helpful links here and below plz

