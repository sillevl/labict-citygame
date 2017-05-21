We used thethingsnetwork\(TTN\) to communicate with the MBED.  
TTN has a library for communicating to devices named ttn.  
We can send data in both ways.  
We also made a websocket with the library wsocket.

## **MQTT \(Message Queue Telemetry Transport\)**

MQTT is a part of the TTN library that we use for the communication with the MBED. It is a machine-to-machine protocol \(M2M\)/"The Things Network" connectivity protocol. We did some research about it to fully understand how this protocol works.

The protocol is useful in places where there is not a very huge bandwidth at your disposal. It is used for sensors communicating with other devices, for home automation and small device scenarios. It is also ideal for mobile applications because of its small size, low power usage, minimised data packets, and efficient distribution of information to one or many receivers.

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

#### HTTP:

* HTTP is **document-centric**.

* HTTP follows the **request/response messaging model**, where client’s need to know the exact address of the device to which it connects.

* HTTP is a **complex protocol** and uses **methods** like **POST, PUT, GET, UPDATE,…** and many return codes.

* HTTP is **text-oriented** and **consumes a lot of network bandwidth**. This might be a high concern for mobile apps users to some extent and such constraint device would not desire such sophisticated protocol as HTTP, **draining the battery** as we all are aware of \(Uses a lot of battery\).

* HTTP does **not have any retry ability or QOS**.

* HTTP is a **point-to-point communication**.

### MQTT methods:

* **Connect**: Waits for a connection to be established with the server.

* **Disconnect**: Waits for the MQTT to finish any work it must do, and for the TCP/IP session to disconnect.

* **Subscribe**: Waits for completion of the subscribe or unsubscribe method.

* **Unsubscribe**: Requests the server unsubscribe the client from one or more topics.

* **Publish**: Returns immediately to the application thread after passing the request to the MQTT client.

### MQTT distribution:

* One to one distribution:  

![](/assets/dist1.png)

There is a publisher \(source device\) who sends data on a certain topic. This data will be received by the broker with the topic. The broker will look for a subscriber \(end device who receives the data\) who is subscribed on the same topic as the publishers topic. Then the broker sends the data to the subscriber. It’s very important that the device who wants to receive the data is subscribed on the same topic as the publishers topic. Otherwise the end device would not receive the data.

* One to many distribution:

![](/assets/dist2.png)

This way of distribution is the same as one to one distribution, but there are more devices subscribed on the same topic. So there are more subscibers who will receive the same data.

* One to zero distribution:

![](/assets/dist3.png)

This way of distribution is the same as one to one distribution, but there are no devices subscribed on the same topic. So there is no device listening to what the publisher sends. But the publisher can keep on sending data, it doesn't have to stop sending.

### MQTT QOS \(Quality Of Service\):

QoS is a major feature of MQTT, it makes communication in unreliable networks a lot easier because the protocol handles retransmission and guarantees the delivery of the message, regardless how unreliable the underlying transport is. Also it empowers a client to choose the QoS level depending on its network reliability and application logic.

There are 3 QOS levels:

![](/assets/QOS.png)

## **TTN\(TheThingsNetwork\)**

Link to package: https://www.npmjs.com/package/ttn





