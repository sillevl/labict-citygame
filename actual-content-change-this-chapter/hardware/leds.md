## LEDs

To have some visual feedback besides the LCD we chose to implement LEDs. 

## TLC59116

The TLC59116 is a constant current 16 channel led driver. Every channel has a 8-Bit PWM register that determines the brightness. This chip communicates via I2C. The reason behind choosing a seperate driver is simple, we do not have enough I/O to not use one. It also makes the software quite a lot cleaner and simpler. 

![](/assets/leddriver.png)