# **Websocket**
For the websocket I've used the library WS.
A websocket is a communications protocol which provides full-duplex communication over a single TCP connection.
### **Why use a websocket?**
We needed the websocket because we wanted to update our map without refreshing the page.
### **How does it work?**
![](/assets/mqttexplained.PNG)
We use the websocket in the part from the listener to our website.
Everytime if there's an update on the thethingsnetwork our listener sends it to the websocket (as you can see in the picture above).
The websocket sends the data to the database and then it gets parsed to JSON format after this we get it out the database to use it on controlpanel.

source: https://en.wikipedia.org/wiki/WebSocket

### **How to install?**
You'll need NPM and powershell for this.
(you can download npm and nodejs here: https://www.npmjs.com/get-npm?utm_source=house&utm_medium=homepage&utm_campaign=free%20orgs&utm_term=Install%20npm)
When you have installed NPM, go to the folder where you want to use the library, open up powershell there and in powershell type: "npm install --save ws" to install the ws library.






