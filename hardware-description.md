# Hardware requirements

## _Game Box_

The "game box" \(one per team\) is a plastic box and will be provided \(see [\#figure-2-vives-game-city-box](#figure-2-vives-game-city-box "VIVES Game City Box") \). The game box will contain the battery, the battery management system, an LCD display, the embedded system, ..., so that the competing teams should have an autonomy of several hours.

![Example of the game box](/assets/SVL_003_2021.jpg)

Let us give an overview of the hardware components:

* battery \(Lithium Ion Polymer - LIPO\)
* battery management system
* FRDM-K64F **mbed **based embedded system \(URL: [https://developer.mbed.org/platforms/FRDM-K64F/](https://developer.mbed.org/platforms/FRDM-K64F/ "FRDM-K64F mbed") - see **Figure 3/4**\)
* Real Time Clock \(RTC\): provide day/time timestamps
* LCD display \(4 x 20 characters\): visualization of messages, tasks, user interface, ...
* keyboard: user input
* key lock
* two LED's: red/blue
* pushbutton

![FRDM-K64F mbed](/assets/FRDM_K64F_large.png)

![FRDM-K64F mbed Block Diagram](/assets/xfrdm-k64f_block-diagram_jpg_pagespeed_ic_n9RhjOFW_9.jpg)

## _Game Box hardware extensions_

The basic hardware of the game box should  be extended with the following hardware components:

* **GPS** module
* **LoRaWAN** transceiver \(URL: [https://www.lora-alliance.org/For-Developers/LoRaWANDevelopers](https://www.lora-alliance.org/For-Developers/LoRaWANDevelopers "LoRaWAN") - see **Figure 5**\) 

**LoRAWAN** is a Low Power Wide Area Network with features that support low-cost, mobile, and secure bi-directional communication for Internet of Things \(IoT\), machine-to-machine \(M2M\), and smart city, and industrial applications. LoRaWAN is optimized for low power consumption and is designed to support large networks with millions of devices. Innovative features of LoRaWAN include support for redundant operation, geolocation, low-cost, and low-power devices can even run on energy harvesting technologies enabling the mobility and ease of use of Internet of Things.

![LoRaWAN Network Architecture](/assets/LoRaWAN_network_architecture.jpg)

