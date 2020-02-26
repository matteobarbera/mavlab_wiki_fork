The standard connection schematics :

![Lisa MXS](https://github.com/tudelft/mavlab/raw/master/photos/drones/nimble/Nimble_wiring.png)

And here the autopilot and SD card connections:


![Lisa MXS](https://github.com/tudelft/mavlab/raw/master/photos/drones/nimble/LisaMXS_nimble.png)


Pay attention:
* in the latest code, the ADC 4 pin on the schematics was remapped as ADC 7
* in the latest code, the ADC 6 pin on the schematics was remapped as ADC 8
* stereocam / monocam / laser ranger might be connected to either Rx3 or Rx4, check in the code you're using

You might want to add a power regulator supplying constant 3.3V power to your receiver (highly recommended) and possibly to the autopilot. However, if you power the autopilot by the power regulator, the onboard voltage reading will stop working (you will see 3.3V all the time). To enable it, you need to rotate resistor R9 on the autopilot board and connect the battery voltage to its free end. Check the [schematics](https://github.com/paparazzi/paparazzi-hardware/raw/master/controller/lisa_s/lisa_mx_s/v1.0/lisa_mx_s_v1_0.PDF) of the Lisa MXS board, or ask for help if uncertain.

<img src="https://github.com/tudelft/mavlab/raw/master/photos/drones/nimble/power_regulator.jpg" width="300">