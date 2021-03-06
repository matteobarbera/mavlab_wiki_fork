This tutorial is written to summarize all the necessary steps to calibrate the OptiTrack system for Delfly use. For more detailed information, please refer to [OptiTrack Documentation Wiki](https://v22.wiki.optitrack.com/index.php?title=OptiTrack_Documentation_Wiki)

**When finishing using the OptiTrack system, before leaving the Cyberzoo, please turn off the Cyberzoo light and leave the curtains open in case of fire hazard.**

## Tool
* OptiTrack CW-500 calibration wand 
* OptiTrack CS-200 calibration square

## Calibration of the camera
* Start calibration procedure by clicking the toolbar `View` and select `Camera Calibration`. The `Camera Calibration` workspace will be shown on the right
![calibration](https://github.com/tudelft/mavlab/blob/master/photos/drones/nimble/optitrack_calibration.png)
* Close the curtains. Move away or turn off any unwanted light sources. If there are still some left, click `Mask Visible` in the `Camera Calibration` workspace to mask those unwanted sources
* Click `Start Wanding` and take the calibration wand inside the Cyberzoo. Wave around the wand under each camera until the light ring turns fully green
* Keep walking while waving the wand until the calibration box in Motive turns green and sufficient samples are collected. A 6-camera system will calibrate properly with an average of 1000 samples per camera 
* Click `Calculate` in the calibration box
* Wait for the calculation to complete and `Apply` the results in the popped window

## Calibration of the ground
* Check the cameras' relative position from the ground in the `Perspective View` panel 
* To start the `Ground Plane` calibration, place the calibration square in the middle of the field, with an orientation shown in the following picture
* Move around the wand to see if the markers show up at the right locations with the newly calibrated ground plane.
<img src="https://github.com/tudelft/mavlab/blob/master/photos/drones/nimble/OptiTrack_calibration_square_orientation.png" alt="alt text" width="250" height="350">


## Track a Delfly
* Select all the markers from a Delfly
* Right click on the selected markers, choose `rigid body`, then `create from selected markers`

## Start recording sessions
* To view the newly created aircraft, click on the toolbar `View` and then `Project`, the aicraft will show in the project menu
* Go to the recording panel by clicking on the toolbar `Layout` and then `Capture`
* Start recording by clicking the record button 
![record](https://github.com/tudelft/mavlab/blob/master/photos/drones/nimble/optitrack_record.png)

## Debug 
Q1: What if the cameras don't collect any samples during the wanding process?
* To start, we should go to toolbar `Edit` and then click `Reset Application Settings`. Please try this before attempting your next calibration, and try not to change many settings to see if Motive is able to calibrate in a default state. 
* When doing the above step, please also check your calibration wand. Currently we have the CW-500, there are two configurations. The markers on the wand must either all be screwed into the "A" holes or into the "B" holes. The two cannot be mixed.

