## Battery System

The projects uses Li-ion batteries \(the ones we used were the ICR18650-22F\) which operate at :

![](/assets/bat.PNG)

The battery management system accommodates for these specifications:

* A minimum voltage is provided through the use of a differential amplifier configured in open loop gain, the reference voltage is provided by a 3V zener diode which is then aplied to the inverting input op the opamp.
  This enables the batteries to not fall below their minimum discharge cut-off voltage of 2,75V as the opamp will have a positive saturation voltage at the output whenever the batteries fall below 3V. A diode protects the mosfets from a negative saturation voltage, ensuring that the mosfets only decouple the batteries whenever they fall below 3V.

* A maximum discharge current is safeguarded through the means of a DC-DC boost step-up converter. As this enables us to limit the maximum current, through the use of external passive components. As well as specifying a  fixed output voltage unanymous of the load needed at an interval. The one issued in this design is a TPS61251. \(More information about the TPS61251 can be found at : http://www.ti.com/lit/ds/symlink/tps61251.pdf\)

![](/assets/Knipsel.PNG)

Lastly as a means to enable communication between the battery managment system and the microcontroller itself, an analog digital converter with an I²C interface was implemented. This basically captures the voltage level of the battery at a certain interval, then codes this analog voltage into a digital code ready for transmission over the I²C line of SDA right to the microcontroller for delivery. The ADC with I²C interface issued in this design is the  ADC081C027 more information can be found at : http://www.ti.com/lit/ds/symlink/adc081c027.pdf

