## Buzzer

The buzzer gives an audible output that corresponds to different actions. Everytime a button on the keypad is pressed, the buzzer will make a beep-sound. When we start our gaming box, a start-up-beep will be heard.


## ABT-414-RC

![](/assets/buzzer_vives.png)

This is the buzzer that we use. The product name is ABT-414-RC, it's a cheap component that you can easily order in the internet. It's also easily to connect to the mbed.


## Connection to the mbed

We connected this buzzer to the pin PTA2 on the mbed.


## Specifications of this buzzer

![](/assets/buzzer_specifications.png)

Read more about this in the datasheet: [Buzzer datasheet](http://www.farnell.com/datasheets/1563662.pdf?_ga=2.202057366.648508541.1495444551-1070812418.1494403917)


## Buzzer code

This is the UML schematic of the buzzer code made in Lucidchart.

If we take a look at the method playNote we can see 3 arguments, namely the frequency \(if you want a higher or lower sound\) the duration of your sound and the volume you want to use. In this way, it is very easy to adapt changes to your sounds. So for example it is very easy to give every key on the keypad a different sound.

We also see a method named startupBeep that gives a sound everytime we start our gamingbox.


![](/assets/Buzzer_UML.png)



