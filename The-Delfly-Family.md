The different Delfly types are presented here. For the DelFly assembly, see [Drone-DelFly-Parts](https://github.com/tudelft/mavlab/wiki/drone-delfly-parts).

- [Delfly Nimble](#delfly-nimble)
- [Delfly Bender](#delfly-bender)
- [Delfly Vector](#delfly-vector)
- [Quadthopter a.k.a. Flappy](#quadthopter-aka-flappy)
- [DelFly II for PIV and system ID](#delfly-ii-for-piv-and-system-id)
- [DelFly Limosine](#delfly-limosine)
- [MilFly](#milfly)
- [Delfly Desperado](#delfly-desperado)

# Delfly Nimble
[Our most agile tail-less design](https://github.com/tudelft/mavlab/wiki/drone-delfly-nimble)


# Delfly Bender
Tail-less design controlled by ropes pulling on the wings

**Scientific paper**: [Wing Sweeping Mechanism for Active Control and Stabilisation of a Flapping Wing MAV](http://www.imavs.org/papers/2018/IMAV_2018_paper_23.pdf)

# Delfly Vector
Tail-less design that uses thrust vectoring for pitch and yaw control

**Scientific paper**: [Attitude control system for a lightweight flapping wing MAV](https://iopscience.iop.org/article/10.1088/1748-3190/aab68c/pdf)


# Quadthopter a.k.a. Flappy
4-wing-pair agile tail-less DelFly controlled like a quadcopter

**Scientific paper**: [Quad-thopter: Tailless Flapping Wing Robot with 4 Pairs of Wings](https://repository.tudelft.nl/islandora/object/uuid%3Ab4fc2b39-b8b1-4791-b071-98557a7254f0)

# DelFly II for PIV and system ID
DelFly II equipped with a Lisa/S autopilot and IR-LEDs. Autonomous flights in [OptiTrack]() possible with a [WiFi]() datalink.
* 2018 campaign (Volumetric PIV)
  * **Scientific paper**: [Large-scale Flow Visualization of a Flapping-wing Micro Air Vehicle](https://www.research-collection.ethz.ch/bitstream/handle/20.500.11850/279239/061a.pdf)
  * [Code](https://github.com/matejkarasek/paparazzi/tree/delfly_optitrack)
* 2017 campaign ("Ring of Fire" approach)
  * **Scientific paper**: [Flow Visuzlization around a Flapping-Wing Micro Air Vehicle in Free Flight Using Large-Scale PIV](https://www.mdpi.com/2226-4310/5/4/99/pdf)
  * [Code](https://github.com/matejkarasek/paparazzi/tree/delfly_piv)
* 2016 campaign (Stereo PIV)
  * **Scientific paper**: [First free-flight flow visualisation of a flapping-wing robot](https://arxiv.org/pdf/1612.07645.pdf)
  * [Code](https://github.com/matejkarasek/paparazzi/commit/50bb921fcec528adf6d11eeb00d1c866992ae372)
* [System ID code](https://github.com/matejkarasek/paparazzi/commits/delfly)
 
<a href="#top">[Back to top]</a>

# DelFly Limosine
DelFly with an extendable main wing to significantly shift the location of the centre of gravity relative to the aerodynamic centre, therefore enabling both stable forward and hover flight:

**Scientific paper**: [Passively Stable Flapping Flight from Hover to Fast Forward Through Shift in Wing Position](https://journals.sagepub.com/doi/pdf/10.1260/1756-8293.7.4.407)

<a href="#top">[Back to top]</a>

# MilFly
The MilFly is the military variant of the Delfly, builded to operate both outdoors and indoors. Modifications include a smaller wing for higher wing-loading for higher speeds.

<a href="#top">[Back to top]</a>

# Delfly Desperado
The Delfly Desperado is a unique Delfly developed by Clement Roblot, equipped with GPS and capable of flying outdoors in winds up to 5m/s fully autonomous. See the following page for more information on how to get a Desperado up and running to fly outdoors: 

[[DelFly Flying via Paparazzi]]

<a href="#top">[Back to top]</a>


