## LoRa Tranceiver

The communication between the box and the game management is done via LoRa. This is relatively new technology that makes it possible to send and receive data with very low power and long range.

### RFM98:

![](/assets/RFMtitle.jpg)

This is the LoRa chip that we use. The RFM98 is cheap and easily available. It communicates with the MBED via SPI. 

### Connection to a gateway:

These LoRa chips can be used to communicate with each other but we use them to send data to a gateway. A gateway is a powerful transceiver with a big antenna that plays the router in between the LoRa network and The Things network. On the site of TTN you can see a map with all the registered gateways.

First thing that has to happen is authentication, this can be done in two ways:
- OTAA: Over The Air Activation -> Authenticates every time it joins the network
- ABP: Activation By Personalization -> Just sents data with known keys

We are using ABP because this is a more flexible for creating the project. When we would use OTAA, the box would keep on trying to make a connection and fail even when it is not possible due to having no gateway in the nearby vicinity.