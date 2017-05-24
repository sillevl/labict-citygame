There are several things that could be added to the firmware in the future. Here are some of these things:

* **Use of the battery level.** There are already parts of the firmware that are made to work with this value. For example, the LCD class has already an icon that can show the player what the battery status is.

  * **Using serial communication to upload the JSON file.** You can make a class that reads the JSON string from a serial connection with a computer. This class must inherit from the `ConfigReader`class. This way it is easy to implement this in the code. An extra addition to this would be saving that string on the eeprom. And creating another class that retrieves this string.  
  
    At this moment there is a stand alone Serial Writing program and a Receiving C++ program.

    To add the Json file we want to use the available serial Port To do so we need a program on the pc who calls the serial port, imports the Json file and then passes it too the serial port of the mbed.

    At the mbed side we need a class who can read the serial port and who can write the incoming information on the SD card.

    Java:

    At the PC side we builded a java program based on the RXTX class. This program contains 4 major parts:

    1. Discover the available COM Ports.

    2. Making connection with the mbed.

    3. Loading the Json file and writing it to the mbed.

    4. Disconnecting and releasing the COM port.  
       Discovery and connecting:  
       ![](/assets/communicatie3.PNG)Selecting and sending the Json file![](/assets/communicatie4.PNG)

  When you start the program you will see this screen:

  ![](/assets/communicatie.PNG)

  The first button simply listens if their are any COM ports with a up status. If so it adds those ports too a list.

  With the second button we select the right port and try to make a connection with it. To do so we fist check if the port is free. if so we init a baudrate and set up a stream in and stream out buffer.

  We use the tirth button when we don't longer need the connection. We end the in- and output stream. Then we release the connection so other users can connect with it.

  If the connection is succesfull we can start writing bytes to the mbed. To do so we can either use the fourth or fifth button.

  The fourt simply converts the string in the textfield into a base64 array and write it byte for byte to the mbed.

  When we use the fifth button we first we locate the Json file and load it into a streambuffer.

  ![](/assets/communicatie2.PNG)

  Then this buffer is converted to a base64 byte array. This buffer is then send byte for byte to the mbed.

  C++

  At the mbed side we have a class who contains 2 parts:

  1. Reading the input stream en writing it to the SD card

  2. Reading the SD card.

  Receiving and writing the data too the SD card

  ![](/assets/communicatie5.PNG)  
  Reading from the SD Card  
  ![](/assets/communicatie6.PNG)

The first methode listens if there’s any incoming date. If so it read the byte into a buffer, then it writes this buffer into a string array. Once there is no more incoming date this array is passed to the SD card.

The second methode reads from the SD card in a simaler way the serial date is received. It reads the file byte for byte and places it into a string array which is passed to the main program for futher use.

Java code: [https://github.com/DevLampe/Serial-Connection/](https://github.com/DevLampe/Serial-Connection/)

C++ code: [https://developer.mbed.org/users/nnoitre/code/SD\_ReadWrite\_K64/](https://developer.mbed.org/users/nnoitre/code/SD_ReadWrite_K64/)

* **More missions.** This is fairly simple to do, once again by using inheritance. By inheriting from the Mission class you can add for example a code mission where the user must enter a number or passcode to complete it.



