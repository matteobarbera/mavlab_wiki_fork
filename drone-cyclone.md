# Cyclone

The Cyclone is a hybrid UAS with 2 motors and 2 flaps. In hover it is dependent on the flow of the propellers to provide dynamic pressure on the flaps.

![Cyclone](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/cyclone.jpg)

## How to build

Murat (ENAC) has molds, which will yield the most beautiful aircraft. Alternatively, it is possible to make one with 3D printed pieces, and laminating a foam wing with aramid (Kevlar).

Ingredients:
* Vacuum bagging equipment
* Foam wings
* Epoxy glue
* Aramid (==kevlar)
* 2x AXI 2808/24 motor
* 2x [MKS HV6130](https://www.hyperflight.co.uk/products.asp?code=MKS-HV6130) servo. This servo needs to work on 8V. Alternatively, try [KST DS125MG](https://www.hyperflight.co.uk/products.asp?code=KST-DS125MG&name=kst-ds125mg-wing-servo-7-0kg-cm-0-12s-27g-10mm).
* [Jeti SBEC](http://www.jetimodel.com/en/katalog/Accessories/BEC-Regulators-Switches/@produkt/SBEC/) or equivalent in order to have the servos on the right voltage
* 2x [Propeller 8"x5](https://flyduino.net/HQProp-8x5B-2032cm-Bullnose-Propeller-Set-black-4-pcs-glass-reinforced)
* 2x 24A KISS race ESC
* Ublox NEO-M8N GPS + HMC5983 compass
* Chimera Paparazzi Flight Controller
* Carbon spar
* 3D printed pieces (files attached, be careful: thickness 3mm, which is intended with 40% fill ratio. This will be heavy if solid!)
* A new scalpel (makes cutting the foam 100x easier)

First, make both sides of the foam wing using the hot wire machine (I don't know the profile, or how to do this). When you have the two pieces, cut them to size: 44cm long, ?cm width at center, ?cm width at tip. Next, cut a slot for the carbon spar.


![Wing with spar](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/wing_with_spar.jpg)


Wet sand the carbon spar and clean with acetone to prepare the surface for glueing. Glue the wings together with the spar using epoxy. Now cut away foam for the ESCs, servos and wires. Cut out the ailerons and taper the edges to allow free rotation for a minimum of 30 degrees in both ways. Now make two slots in each aileron and in each wing, where the hinges will come. The hinges will need to be in the center of the airfoil. As the hinges, use small teflon squares.

Add a carbon spar in each of the flaps. It should help the torsion stiffness, so probably a round profile is best. Also cut out space for the servos.

![Flap with spar](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/flap_with_spar.jpg)


Cut away foam for the ESCs and the wires.
Drill a hole in the motor mount for the wires to go through and cut away some foam such that they can reach the ESC.
Attach the motor to the motor mount with four bolts.
Now center the servos and attach the servo arm in the neutral position. 
With the Teflon hinges in place, glue the servos with epoxy, and glue the flap to the servo arm.

![Servo](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/servo.jpg)

Use epoxy to glue the motor mounts to the wing.
Glue the Teflon hinges simply by putting a bit of super fluent "thin CA" on the hinge, which will be sucked in to the slots. (Alternatively, the hinges may be made out of kevlar. The procedure for this is to put epoxy in the slot, and push in a piece of kevlar. Once it is cured, attach it to the wing.)

![Motors](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/motors_attached.jpg)


When this is cured, use a servo tester to make sure there is no foam blocking the hinge line.
Next, solder the ESC and the wires going to the autopilot.
Make sure to test the direction, such that the propeller will go down at the wing tip and up at the center, opposite to the wing vortex at each tip.
Cut out foam to make room for the cables, because things sticking out will prevent the aramid to touch the foam around it.
Cover the ESCs and cables with a bit of tape, and make sure to cover the servo axis, as they should definitely not get stuck (not yet done in the picture below).
This can be done with foamrubber (glue?), which should be easy to take out afterwards.

![Lamination](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/prepare_lamination2.jpg)
![Lamination](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/prepare_lamination.jpg)


Now it is time to cut the mylar and aramid.
Start with the Mylar by tracing the wing and cutting it with normal scissors.
Make sure to take some extra space at the trailing edge (~1cm or more) and a bit less at the leading edge (we will do the leading edge separately).
Take into account that your wing may be a little bit asymmetric, so pay attention to top/bottom.

Move on to the aramid.
Make sure to handle it with extreme care!
The woven fabric should not be grabbed, as the strains will move, the fabric will deform, and it will not be flat / fit nice any more.
Trace the mylar cut-outs on the aramid, and cut the aramid with special aramid scissors (don't use these scissors for anything else!).
Pay attention to the direction of the fibers!
Because we need torsion stiffness, go for a 45 degree angle.
Cut the aramid on the inside of the drawing, as it should not stick out underneath the mylar.

Prepare a vacuum bag that can fit the wing, with one opening through which you will put the plane.
Also prepare the hose and make sure you know how the pump works.
Note that you should not apply too much pressure, as the foam will be squashed and the original shape will be lost.
Place some tissues in there as 'breather' material.

## Laminating the wing

Prepare everything rigorously, because you will be working under time pressure, and you don't want to find out you forgot something when the epoxy is already applied.
Prepare a big working space, clear the tables, bring tape, tissues, cups, wooden mixing sticks, etc.
Start out by applying the wax on the Mylar with a paper towel, which will make sure that the epoxy does not stick to the Mylar.
Just apply a quantity that you can easily spread to the whole surface.
Next, take a clean paper towel, and work the surface with it, in order to make the layer of wax as thin as possible.

Now, gently put the aramid on the mylar.
It may be that you have stretched it by handling it.
In that case, very gently try to push it back into the right shape.
Prepare a few (8) tapes, which you can use once you need to fix the mylar+aramid to the wing.

Now it is time to mix the epoxy (--wear gloves!--), for which it is best to be with 2 persons.
Remember to check the time, such that you know when you cannot work with it any more.
You should not need more than 60 grams.
Start by pouring some of the epoxy across each of the mylar/aramid combos.
Use a piece of foam to spread the epoxy over the surface.
Do this not by wiping, as this will deform the aramid, but by pushing in a rolling motion.
The rolling motion will help to take off the foam sponge without pulling on the aramid too much.

Note that you can spread it more than you think, and less epoxy will mean less weight.
However, you do need to make sure that the whole sheet has epoxy, and consider that a bit more epoxy may make it a bit more resistant against de-lamination.
At the same time, the more epoxy, the more will go into places where you do not want it, such as the hinges.

When finished, place the wing on the bottom part and place the top part on it.
Use the tapes to fix the mylar in place.
Put it on top of the tissues inside of the vacuum bag, and add some tissues on top.
This will ensure the air can still flow through something.
Seal the bag and apply pressure (again, not to much).

![Lamination](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/lamination.jpg)

![Out of the bag](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/out_of_bag.jpg)


Take it out when the curing time is over.
Remove edges with a sharp scalpel and free the hinges.

The next step is to cover the leading edge with aramid.
Instead of with a vacuum bag, we can simply do this by waxing pieces of plastic, putting strips of aramid with epoxy on them and taping this tightly around the leading edge, as shown below.

![Leading edge](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/leading_edge.jpg)


Take special notice that you should try to remove any air pockets, as these will not be attached to the skin, and may be a source of delamination (see the image below).

![Air pockets](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/airpockets.jpg)


Cut the aramid such that you can access the wires of the servos and the motor controllers.

![Free wires](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/free_wires.jpg)

Solder the power wires together with the wires of the ESC and the power wires for the autopilot board (and potentially the power supply for the servos).
Test if the power harness works before you glue the autopilot in place.

![Connect](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/connect.jpg)

This can be done by attaching nylon bolts to to the autopilot, and gluing the the bolts to the aramid with hot glue (other glues don't work well on nylon).
This way, you don't need to put glue on the autopilot itself.

Glue the back fuselage part to the wing, but be sure to check that it has a good fit together with the top parts!
Otherwise, you can end up with the following:

![Fuselage on wing](https://github.com/tudelft/mavlab/raw/master/photos/drones/cyclone/fuse_glue_on_wing.jpg)

