# Current equipments

The MAVLab is now equipped with three 3D printers: 
* the Ultimaker 3
* the Anycubic Chiron
* the Anycubic Photon (resin printer, restricted access)

The Cura slicer is available at https://ultimaker.com/software/ultimaker-cura. 

## Ultimaker 3

The Ultimaker 3 printer has a printing volume of **215 x 215 x 200 mm**. Leveling is automatic and printing material must have a diameter of **2.85 mm**. To setup the printer profile on Cura, simply go to `Settings > Printer > Add printer...` and pick up the Ultimaker 3. Recommended print setup should normally be enough for most printings. 

**Printing LightWeight PLA with Ultimaker 3**

Not long ago Colorfabb released a new PLA-based material called LW-PLA(LightWeight-PLA). This material has the peculiarity to foam up during the extrusion process decreasing the density of the printed material. The density of the LW-PLA could go up to 50% of the classic PLA in certain application. More info about the LW-PLA can be found at the following Colorfabb link: https://colorfabb.com/lw-pla-natural. 
TU Delft, as institution has a special 20% discount on all the Colorfabb filament. You can contact [Alessandro](mailto:a.mancinelli@tudelft.nl) to know how to use it. 
Some printing tests have been performed in order to determine the best printing settings for this specific material using CURA as slicer. 
The printing parameters can be directly imported using the or can be manually filled in as in the picture below:



## Anycubic Chiron

The Anycubic Chiron 3D printer offers a large printing volume of **400 x 400 x 450 mm**. It comes with both manual and automatic leveling systems, and requires **1.75 mm diameter** print material like PLA. You can use the [official user manual](https://github.com/tudelft/mavlab/blob/master/pdf/equipment/ANYCUBIC%20Chrion-User%20manual-20180907-V7.pdf) to setup the slicer profile. 

Prior to the printing setup, you will be required to setup your 3D printer on Cura. Since the Anycubic Chiron is not available on the printers list, select the **Prusa i3** basic model and then change the machine settings to get the same as described below. 

<img src="https://github.com/tudelft/mavlab/blob/master/images/anycubic_chiron_cura_printer_settings.png" width="75%"/>

<br/><b>Using Renkforce PLA Filament?</b><br/>
Print settings depend on the material you are using. If you are using Renkforce PLA filament (1.75 mm), you will need to adjust the print settings. You can either use the [Cura settings for Renkforce](https://github.com/tudelft/mavlab/blob/master/scripts/Chiron_Cura_Profile.curaprofile), or directly set the parameters as follows: 

<img src="https://github.com/tudelft/mavlab/blob/master/images/Chiron_Printing_Params.png" width="50%"/>

It is highly recommended to disable the initial extrusion of filament (generally 3 mm of stock material). You can do it by modifying the  "Start/End-Gcode" tab in Cura. There should be a line saying something like: G1 F200 E3              ;extrude 3mm of feed stock. The number after the E is the amount of filament (in mm.,) extruded before the print starts. Replace 'E3' by 'E0'.

<br/><b>Troubleshootting</b><br/>
For some reasons, the first layer is a bit tricky when using Renkforce filament. Please pay attention to this early phase. For a better result, it is recommended that you use **tape** or **adhesive spray** on the bed plate. 

## Anycubic Photon (restricted access)

The Anycubic Photon 3D resin printer comes with high printing resolution: 47-microns XY resolution, 1.25-microns Z accuracy, with an overall build volume of 120 x 68 x 150 mm. To print with this device, please use the 405-nm UV resin. For instructions on how to print, please watch the following [video](https://youtu.be/VLZbEj4W8O4).

* [User manual](https://drive.google.com/file/d/1gGvgaVlVSFrv6Ad0xq8NZv_crqn2u_rz/view)
* Suggested layer thickness: 25 - 100 microns
* Suggested print speed: 10 - 18 mm/hour

The powering cables are not available in the MAVLab. If you want to print something, please contact either [Julien](mailto:j.j.g.dupeyroux@tudelft.nl) or [Diana](mailto:d.a.olejnik@tudelft.nl). 

The Anycubic Photon Slicer software is only available on [Mac](https://github.com/ANYCUBIC-3D/PhotonWorkshop/releases/download/v2.1.21/Photon_WorkShop_V2.1.21.dmg) and [Windows](https://github.com/ANYCUBIC-3D/PhotonWorkshop/releases/download/v2.1.21/Photon_WorkShop_V2.1.21.exe). For Linux users, it is recommended to use the open-source [Chitubox](https://www.chitubox.com) software. Chitubox already includes the settings required for printing with the Photon printer: `Settings > Add Printer > ...`.

**RESIN PRINTER SAFETY RULES**

* ALWAYS WEAR GLOVES WHEN MANIPULATING THE RESIN!
* During the printing phase, use the plexiglass panel to prevent from smell spreading in the MAVLab.
* After each printing, remove the remaining resin from the tank, filter it out and place it back into the UV-resin bottle. Then, carefully clean the tank. 

You can also have a look at the following video to have a clear overview of the safety rules you must keep in mind when working with a resin printer: [Resin 3D Printing Safety for Beginners](https://www.youtube.com/watch?v=7kHcsTG9QsM)

After printing, remove the part carefully and then clean it by means of the ultrasonic cleaner. The cleaning duration obviously depend on the size of your print, but something like 5-15 minutes should be enough. You may find interesting tips [here](https://www.kudo3d.com/post-process-your-sla-prints-in-4-easy-steps-2/). Use Isopropyl Alcohol (IPA) in the cleaning tank to clean the part. Once this is done you will need to cure the print using the curing chamber. Instruction sheet can be found next to it. 

*More information to come soon.*