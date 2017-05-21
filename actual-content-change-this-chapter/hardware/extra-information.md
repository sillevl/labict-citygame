## Extra Information

In this part I want give some detailed information on how to use and expand the hardware.

## Soldering the hardware

There are some things to keep in mind when soldering the hardware, here is a list:
- Make sure to solder the JST connectors on the bottom side of the board. Otherwise connecting the other components will be quite difficult. 
- If there is a problem with the second row on the keypad. Solder the ROW2 pin to PTB20
- Bridge all the two pads of the solder jumpers that are most to the side of the board. When using the Microchip Lora, choose the other two. (Not tested)
- The diodes (D2-4) are not really necessary these can be jumped with a bit of wire.
- The 2 pin VBAT JST connector is also not necessary. Would you want to connect the backup battery voltage to the mbed chip. You could use these pins.
- Please mind the correct polarity of the voltage connector. The 5V pin is marked with "5V!".

These were some issues in the first revision of the board:
- The 7 pin JST connector holes are too small. The connector should be mounted 90 deg to fix this.
- The R/W pin of the LCD is not connected to ground. Wire a small cable that does that. 
- Do not solder C4, this can interfere with the Microchip lora module.

The updated version does not have these problems.

## Hardware upgrades

There are some thing to upgrade or to expand on. Here is a list:
- Would you wish to add a sensor, you can use the 4 pin JST I2C expander connectors. These are connected to 5V straight from the input so these can handle some current.

- Currently there is not a fully implemented battery system. The original plan was to use one of these expander ports to connect to the BMS and read out the battery voltage. 

- There is a Adafruit Compass header on the board that can be used to solder that module on. 

## Board & Schematic files

The board and schematic files can be found on the following GitHub page:
https://github.com/thomieboy/VivesCityGame-Eagle