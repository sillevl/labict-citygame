## ARM Processor

#### Introduction

The **Freedom-K64F** is an ultra-low-cost development platform. The flagship **FRDM-K64F** has been designed by NXP in collaboration with mbed for prototyping all sorts of devices, especially those requiring optimized size and price points. The board is well sized for connected applications, thanks to its core that is **running up to 120MHz** and **embedding 1024KB Flash***, **256KB RAM** and lots of **peripherals** (16-bit ADCs, DAC, Timers) and **interfaces** (Ethernet, USB Device and Serial).

For more information click [here](https://developer.mbed.org/platforms/FRDM-K64F/).

![](/assets/frdm.JPG)

#### FRDM-K64F hardware overview

![](/assets/overview.JPG)

#### FRDM-K64F hardware description

###### Power supply

There are **multiple power supply options** on the FRDM-K64F board. It can be powered from either of the **USB connectors**, the **Vin pin on the I/O header**, **DC Jack** (not populated), or an **offboard 1.71-3.6 V supply** from the 3.3 V pin on the I/O header. The USB, DC Jack, and Vin supplies are **regulated onboard** using a 3.3 V linear regulator to produce the main power supply. DC to DC linear regulator is **not available in 3.3 V on J20 Header**, however a direct supply to K64 MCU is available.

The table below provides the operational details and requirements for the power supplies:

|Supply source | Valid range |
|--------------|-------------|
|OpenSDAv2 USB|5V|
|K64 USB|5V|
|Vin Pin|5 - 9V|
|3.3V Header (J20)|1.71 - 3.6V|
|DC Jack (Not populated)|5 - 9V|

The **OpenSDAv2 circuit is only operational** when a USB cable is connected and supplying power to `OpenSDAv2 USB`. However, the protection circuitry is in place to enable multiple sources to be powered at once.

###### Serial and Debug Adapter version 2 (OpenSDAv2)

OpenSDAv2 is a **serial and debug adapter circuit** which **includes** an **open-source hardware design**, an **open-source bootloader**, and **debug interface software**. It bridges serial and debug communications between USB host and an embedded target processor as shown in the figure below.

![](/assets/OpenSDAv2.JPG)

###### User's guide

For additional information, you can click on the next link:
[User's guide](https://developer.mbed.org/media/uploads/GregC/frdm-k64f_ug_rev0.1.pdf) 

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