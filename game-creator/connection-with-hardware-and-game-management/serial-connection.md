# Serial Connection

## The Communicator

We created a communicator app which is able to send a JSON file to an SDcart. This small app was supposed to open up whenever the user clicked connect, but due to lack of time we werent able to fully implement this and get it to work with the entire project. 

![](/assets/connect 2.png)

![](/assets/Communicator.png)

As you can see this application has a lot of different buttons:

*  Discover COM: the Discover COM searches for storage devices
* Connect: connects to a storage device
* Disconnect: disconnects the storage device
* Send Data: Sends the chosen file to a connected storage device
* Choose File: opens a filechooser where you can search for the desired JSON file

When you click the **Choose Files** button, a new window will open which lets you search in your pc directories for the desired

![](/assets/file chooser.png)

This Communicator relies on the java RTRX library

