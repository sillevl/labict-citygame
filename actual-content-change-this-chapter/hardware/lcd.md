![](/assets/LCD_Title.jpg)

### Hardware

**Connect LCD to mBed:**
* Connect following pins from the LCD to the mBed:

id  | LCD | mBed | Description
----|-----|------|------------
GND | 1   | GND   | Ground for lcd
VDD | 2   | 5V    | +5V for LCD
CA  | 3   | 10K   | Contrast adjustment
RS  | 4   | PTC5  | Register select
R/W | 5   | GND   | Read/write
E   | 6   | PTC7  | enable
D0  | 7   | NC    | Data 0 (not connected)
D1  | 8   | NC    | Data 1 (not connected)
D2  | 9   | NC    | Data 2 (not connected)
D3  | 10  | NC    | Data 3 (not connected)
D4  | 11  | PTC0  | Data 4
D5  | 12  | PTC9  | Data 5
D6  | 13  | PTC8  | Data 6
D7  | 14  | PTC1  | Data 7
VDD | 15  | +5V   | +5V for led
GND | 16  | GND   | Ground for led


[Datasheet](https://www.sparkfun.com/datasheets/LCD/GDM2004D.pdf) of the 20x4 LCD

### Software

![](/assets/UML.png)

####Methods:

- *setBacklight:*
        float value between 1 and 0, 1 = 100% backlight and 0 = 0% backlight
        This method changes the pwm value that controls a transistor that controls the backlight leds.
        note: reduce backilght to preserve battery life

- *setTime:*
        Sets the time for the topbar.

- *setStatusBattery:*
        Float between 1 and 0, 1 is 100% battery 0 is 0% battery.
        This methode wil change the battery icon in the topbar.

- *setStatusLora:*
        First argument sets lora icon, second sets RX, TX or idle icon next to the lora icon.

- *setTopBar:*
        Bool that enables or desables the topbar, when topbar is desabled screens are coped to 4 rows                 instead of 3.
        
#####Other methods are self explanatory.     



#### Display driver:

[Source code](https://developer.mbed.org/users/atomicLogic/code/TextLCD/)
    


#### Display interface:

[Source code](https://developer.mbed.org/users/atomicLogic/code/DisplayDriver/)







