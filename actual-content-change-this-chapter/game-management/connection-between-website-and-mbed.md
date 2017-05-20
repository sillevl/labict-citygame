We used thethingsnetwork\(TTN\) to communicate with the MBED.  
TTN has a library for communicating to devices named ttn.  
We can send data in both ways.  
We also made a websocket with the library wsocket.

## **MQTT \(Message Queue Telemetry Transport\)**

MQTT is a part of the TTN library that we use for the communication with the MBED. It is a machine-to-machine protocol \(M2M\)/"The Things Network" connectivity protocol. We did some research about it to fully understand how this protocol works.

The protocol is useful for connections with remote locations where a small code footprint is required and/or network bandwith is not that big. It is used for sensors communicating to a broker via satellite link, over accasional dial-up conections with healthcare providers and in a range of home automation and small device scenarios. It is also ideal for mobile applications because of its small size, low power usage, minimised data packets, and efficient distribution of information to one or many receivers.

### MQTT vs HTTP:

#### MQTT:

* MQTT is **data-centric**.
* MQTT is a **reliable and light transport protocol** that permit TTN devices to communicate with other devices.
* This protocol **uses really few bytes** to describe the content of the messages, so it can be very useful to adopt in a context where we need to exchange small messages and when we don’t have a great bandwidth \(**uses lesser bandwidth**\). **It transfers data as a byte array**.
* MQTT is typically used for **communication between machine to machine**.
* MQTT is a simple **pub-sub messaging system** \(**publisher-subscriber**\) which is loosely coupled, which allows client’s existence independent of any other device and is a **bidirectional communication channel**.
* MQTT is **a more developer oriented protocol** with **less specification**, **methods** \(Subscribe, Publish, Connect, Disconnect, Unsubscribe\), and **message types**.
* Header of a MQTT message has a **size of 2 bytes** and the **message itself is in binary format**.
* MQTT **supports 3 QOS levels** out of the box in message publication, which makes developers life easy as there is no requirement to write complex, additional logic to ensure message delivery.
* MQTT has a built-in distribution mechanism, supporting **one to one, one to many, one to zero distribution models**.



