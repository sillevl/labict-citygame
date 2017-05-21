There are several things that could be added to the firmware in the future. Here are some of these:
- **Using the battery level.** There is already parts of the firmware that are made to work with this value. For example, the LCD class has already an icon that can show the player what the battery status is.

- **Using serial communication to upload the JSON file.** You can make a class that reads the JSON string from a serial connection with a computer. This class must inherit from the ```ConfigReader```class. This way it is easy to implement this in the code. An extra addition to this would be saving that string on the eeprom. And creating another class that retrieves this string. 

- **More missions.** This is fairly simple to do, once again by using inheritance. By inheriting the Mission class you can add for example a code mission where the user must enter a number or passcode to complete it. 
