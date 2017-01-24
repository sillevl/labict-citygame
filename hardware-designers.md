# Tasks of the Hardware Designers

The non limiting list of tasks of the hardware designers is:

* development of the **mbed device drivers**
* integration of the mbed firmware in **mbed OS **
* development of the **Battery Management System** \(BMS\)
* communication with the software development team, Agile **SCRUM** Software Development Methodology

#### _mbed device drivers_

The mbed** **device drivers should be developed according to the Object Oriented Paradigm \(OOP\), for instance in C++. For each device that will be interfaced by the mbed, the driver software should be based on at least one **class**. A recommended approach is to divide the software in at least three sections: the **interface** \(e.g. GPSmodule.h\), the **implementation **\(e.g. GPSmodule.cpp\) and **application** \(e.g. GPStest.cpp\) \(see **Figure 5**\).

#### Figure 5: OOP Interface/Implementation approach

![](/assets/OOP.png)

#### _integration of the mbed firmware in mbed OS_

ARM mbed OS is an open source embedded operating system designed specifically for the "things" in the Internet of Things \(see **Figure 6**\). It includes all the features you need to develop a connected product based on an ARM Cortex-M microcontroller, including security, connectivity, an RTOS, and drivers for sensors and I/O devices.

URL: [https://www.mbed.com/en/development/mbed-os/](https://www.mbed.com/en/development/mbed-os/ "mbed OS") 

#### Figure 6: mbed OS

![](/assets/mbed_os_server.png)

#### _**Battery Management System \(BMS\)**_

The output voltage of the LIPO battery will be +3,7 V DC. This voltage should be transformed to +5 V DC. A DC/DC convertor could be a valuable suggestion. The game box should have to ability to charge the battery. The external connector for charging the LIPO battery must be an USB connector. A **Battery Management System** \(see **Figure 7**\) is mandatory to prevent excessive discharge of the Lithium-Ion battery. Deep discharge of this kind of battery would cause irreversible damage to the battery.

#### Figure 7: Lithium-Ion Battery Management System

![](/assets/BMS2.jpg)

#### _**Communication with the software development team**_

The team of hardware developers should communicatie on a regular basis with the software development team. The iterative and incremental Agile software development methodology of **SCRUM** \(see **Figure 8**\) is advised. One of the major contributors to the succesful realisation of  a project is an intense, regular communication between the hardware and the software engineering teams. Detailed agreements on interfaces, connectors, communication protocols, pinout, ... are mandatory and fundamental to guarantee the succesful realisation of your project within a realistic period of time.

#### Figure 8: the Agile SCRUM Methodology of software development

![](/assets/SCRUM.jpg)

