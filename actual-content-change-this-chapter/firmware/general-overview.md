## General overview

### UML
![](/assets/Simplified UML.png)

This simplified UML show the general nesting of all the classes within the VivesCityGame firmware. There are three main things to know about this:
- All the hardware classes are linked to the board class. That is how the program communicates with the hardware. At the start of the program an object of the board class is created. That object can be passed trough to a mission or game object so that we can ask the LCD to display something. 
- We are using creator classes to create our missions and game. We just pass on the JSON string and the GameCreator class returns a complete game class. 
- The missions inherit from a super class ```Mission```, this way it is fairly easy to implement new missions. 

### Flowchart
![](/assets/Longer Version Of UML run.jpg)

This simple flowchart shows how the firmware works. We start off with initializing the logger. The logger periodically logs the location and mission status to the serial port. Then we initialize the Board. This creates objects of all the hardware classes and calls a few methods on them. After that we read in the Json and pass this on to the GameHandler class that passes this on to the GameCreator class. There, a complete game is set up and returned back. Then the GPS read & Lora send thread are started.
When all the init parts are done the program goes into an infinite loop and just waits until there is a GPS fix. A GPS fix means that a semi-reliable location has been determined with the data of at minimum 3 satellites. When there is a fix the program just calls the run method on the gamehandler. That run method asks the current mission if it is completed. When it is complete, the next one is loaded. If not, the program just continues the cycle.