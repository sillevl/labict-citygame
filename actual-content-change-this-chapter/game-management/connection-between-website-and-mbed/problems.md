## **Problems **
The issue I had with this task was that it took way too long.
I never used NodeJs and MQTT before so it was all new for me.
It took a lot of testing to get it working.
I first started with a connection to a raspberry Pi when this worked I tried to make a connection with the MBED.
I've lost a lot of time trying to make it work as perfect as it could be.
The second issue was sending data back to the mbed.
We needed to make an encoder to encode our JSON.
I've searched on the internet but found some things after that i've made a topic on the forums of TTN.
There they suggested that I use base64 to encode the JSON.
With their help it worked.
The only problem that still exist is that now it sends everytime if the MBED sends data to us.
