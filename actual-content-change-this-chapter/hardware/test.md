## ARM Processor

#### Introduction

The **Freedom-K64F** is an ultra-low-cost development platform. The flagship **FRDM-K64F** has been designed by NXP in collaboration with mbed for prototyping all sorts of devices, especially those requiring optimized size and price points. The board is well sized for connected applications, thanks to its core that is **running up to 120MHz** and **embedding 1024KB Flash***, **256KB RAM** and lots of **peripherals** (16-bit ADCs, DAC, Timers) and **interfaces** (Ethernet, USB Device and Serial).

For more information click [here](https://developer.mbed.org/platforms/FRDM-K64F/).

![](/assets/frdm.JPG)

#### Pinout

###### UART

The **UART** is one of the serial I/O modules from the **FRDM-K64F** board. The **UART** provides a full-duplex, asynchronous communication channel, which allows communication with peripherals and computers by means of **Serial Protocols**.

###### I²C

With **I²C**, **serial data `(SDA)`** and **serial clock `(SCL)`** lines are shared between all I²C slave devices, but the addressing scheme happens by **sending a message heard by all devices on the bus**. To single out one device on the shared bus, the **master first passes down the address** of the slave device it wants to talk to, after which that **slave replies with an ACKnowledge**, and all **other slaves ignore the data that follows** until both data transmissions is complete and the bus is released.

###### SPI

**SPI**, like I²C, is another protocol that shares both its **serial data `(SDA)`** and **serial clock `(SCL)`** lines with multiple slave devices. The difference, though, lies in the addressing scheme to talk to these devices that share the same bus. With SPI, while **clock and data lines are shared**, devices are addressed with separate **chip-select `(CS)`** lines.

The master microcontroller dedicates a **unique output pin** to each device (SS1, SS2, and SS3 in this illustration below). When the master microcontroller wants to **talk to a device**, it asserts that device's **chip-select** input pin by **pulling it to logic LOW**, and the conversation begins over the data bus. With the **chip-select LOW**, the corresponding slave listens to the data on the bus. Meanwhile, all **other devices ignore the conversation** between the master and it's chosen slave by **keeping their bus pins** in a **high impedance** state.

![](/assets/SPI.JPG)

###### Header pinout

![](/assets/pinout.JPG)