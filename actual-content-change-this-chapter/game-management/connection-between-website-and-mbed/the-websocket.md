## **Websocket**
For the websocket I've use the library ws.
### **Why use a websocket?**
We needed the websocket because we wanted to update our map without refreshing the page.
### **How does it work?**
![](/assets/explanation connection - Page 1.png)
We use the websocket in the part from the listener to our website.
Everytime if there's an update on the thethingsnetwork our listener sends it to the websocket (as you can see in the picture above).
The websocket sends the data to the database and then it gets parsed to JSON format after this we get it out the database to use it on controlpanel.



