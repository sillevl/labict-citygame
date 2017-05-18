## PCB Design

All these components need to be connected to each other. The PCB handles this. 
***
### Main PCB
#### Schematic
![](/assets/Afbeelding2.png)

This is the complete schematic. I will go into detail about some parts of the schematic. 

##### I2C Expander JST
In the top left there are the JST connectors for I2C expansion. The led board is also connecting to the board via on of these. 

##### Solder Jumpers
There are solder jumpers in the schematic due to the addition of another Lora chip. We added the possibility to use the Microchip Lora chip that uses Serial for its communication. The serial pins were already in use by the GPS so we need to use other ones. There is a second serial available but these are once again already used for I2C communication. So these jumpers are meant to select between the normal I2C or the secondary I2C. This way it is still possible to use the Microchip Lora.

##### EEPROM
There is an 1M eeprom available that communicates via I2C. But this one has not been used in the current implementation of the firmware. The memory could be used to store a json file.

##### Switch & Buttons
These are also connected via JST headers. I used a normal pull down config here.

##### Buzzer
The buzzer is driven by a transistor. The base of this transistor is attached to a PWM port. This way it is fairly simple to generate a frequency.

##### LCD
The LCD is attached in 4 bit mode. This means that the 8 bit commands are sent in two parts. This saves quite some pins. On thing I forgot to do in the first revisions of the PCB is to pull the R/W pin to GND. This was the reason why the LCD didn't work. 

##### GPS
The GPS is on the bottom right. There is a backup battery clip that makes it possible to hot start the GPS chip. This way it takes a lot less time to find its GPS info. The reason behind this is that the chip can remember its time. And that is a key component in calculating its distance to various satellites. We are also using the GPS chip as an RTC for the application.

##### Keypad
Above the GPS chip is the keypad. All the rows are pulled down with a resistor. The rows have diode in series which we did not use afterward. I was thought this was necessary because there could be a short if the column pins are on a different voltage level and you would press two buttons at the same time.  

  
#### Board
Top Layer:
![](/assets/Afbeelding3.png)

On the front side of the PCB there isn't much. We did this on purpose to make it easy to debug when the board is mounted. As you also may notice, the GPS chip (top left) and the Lora chip (underneath) are placed very close to the edge. That is because the chips has to be as close as possible to the SMA connector to make sure there is no interference on the signal. That is also the reason why there are vias around the signal trace, this forms a sort of shielding.

Bottom Layer:
![](/assets/Afbeelding4.png)
#### Result
![](/assets/Afbeelding8.jpg)
***
### Led Board
#### Schematic
![](/assets/Afbeelding5.png)
#### Board
![](/assets/Afbeelding6.png)
#### Result
![](/assets/Afbeelding7.jpg)
***
### Pinout



### Other interesting trivia

***
## Finished Product
![](/assets/colage.jpg)