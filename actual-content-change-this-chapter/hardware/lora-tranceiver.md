## LoRa Tranceiver

The communication between the box and the game management is done via LoRa. This is relatively new technology that makes it possible to send and receive data with very low power and long range.

### RFM9X: \(We are actually using the RFM96\)

![](/assets/RFMtitle.jpg)

This is the LoRa chip that we use. The RFM9X is cheap and easily available. It communicates with the MBED via SPI.

### Connection to a gateway:

These LoRa chips can be used to communicate with each other but we use them to send data to a gateway. A gateway is a powerful transceiver with a big antenna that plays the router in between the LoRa network and The Things network. On the site of TTN you can see a map with all the registered gateways.

First thing that has to happen is authentication, this can be done in two ways:

* OTAA: Over The Air Activation -&gt; Authenticates every time it joins the network
* ABP: Activation By Personalization -&gt; Just sends data with known keys

We are using ABP because this is more flexible when creating the project. When we would use OTAA, the box would keep on trying to make a connection and fail even when it is not possible due to having no gateway in the nearby vicinity.

### Data:

The data sent to TTN is in byte format. We are currently using 8 bytes to send the following values:

* Latitude
* Longitude
* Mission ID
* HDOP

These values need to be converted into a JSON string so the Game Management can easily use the values on their site. This is done by a decoder on the TTN site.

```
function Decoder(bytes, port) {

  var mission = bytes[6] * (1 << 8) + bytes[7];
  mission = mission < 32767 ? mission : mission - 65535;

   return {
     lat    : ((bytes[0] * 256 * 256 + bytes[1] * 256 + bytes[2]) / 16777215 * 180) - 90,
     long   : ((bytes[3] * 256 * 256 + bytes[4] * 256 + bytes[5]) / 16777215 * 360) - 180 ,
     mission : mission,
     hdop   : bytes[8],
  };
}
```



