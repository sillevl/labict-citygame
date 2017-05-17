## GPS Chip

We need the user's location to know if he is where he needs to be. The GPS module will take care of that for us.

## Adafruit Ultimate GPS Module

![](/assets/GPStitle.jpg)

We are using the Adafruit Ultimate GPS. A powerful, robust and feature rich module build on the MTK3339 chipset. You can request the location ten times a second while only drawing 20 mA. This module has a built in antenna but it is recommended to use an external one.

## Communication with MBED

The chip communicates via a normal serial TTL level protocol at 9600 baud. (Can be changed) The data protocol uses the MTK NMEA Packet Format.

![](/assets/GPSprot.PNG)


