## How does the game work? 

This part will explain how to use the box itself and what you can do with the software.
- First we need a JSON file from the game creators, for reference this JSON file should look a bit like this.
```json
{
   "name":"LocationGame",
   "box_description":"Go to locations.",
   "full_description":"Whilst bringing the rebels to the imperial prison, your stardestroyer got shot. Retrieve the lost communicator parts to contact an extraction team",
   "length":3000,
   "time":120,
   "missions":[
      {
         "id":1,
         "name":"GotoLocation",
         "description":"The first part is at the entrance of Kinepolis",
         "typeid":10,
         "locations":[
            {
               "lat":51.223142,
               "long":2.896536,
               "radius":20.3
            }
         ]
      },
      {
         "id":2,
         "name":"GotoLocation",
         "description":"The next one is at the Spar",
         "typeid":10,
         "locations":[
            {
               "lat":51.222359,
               "long":2.892109,
               "radius":15.5
            }
         ]
      },
      {
         "id":3,
         "name":"FindAKey",
         "description":"There is a key on the light pole",
         "typeid":20
      }
   ]
}
```

- We need to **minify** this long string. That means that there should be no spaces or new lines in the string. You can do this on this site: 
http://www.cleancss.com/json-minify/ 
- After minifying we need to **escape** the characters "\ etc. This can be done on this site:
https://www.freeformatter.com/json-escape.html
We need to copy and paste this string between the two  " " marks in the main program. (main.cpp) 
The # symbols are placeholders for that string.
```cpp
ConfigReader * reader = new StringReader("###########");
```

- Compile and upload the software onto the mbed. If the mbed hangs or crashes there is something wrong with the string. Make sure the radius number are for example 20.0 and not just 20.

- Make sure both the GPS and LoRa antennas are properly attached.

- You are greeted with a welcome screen.

![](/assets/Welcome LCD.jpg)

- After that a menu screen. There are two options. Start the game or go to the status screen. To move the arrow you must use the keypad. It uses the following configuration.

|Key|Function|
|-------|---------|
|2|Up|
|4|Back|
|5|Select|
|6|Next|
|8|Down|


![](/assets/Menu LCD.jpeg)


- The status screen should show the current battery level, but this is not implemented yet. To start the game just choose the first option.

- The LCD will probably show "Waiting for gps". This means that there is no fix yet. Make sure that the GPS antenna is close to a window or that you are outside in an open area. 

![](/assets/GPS LCD.jpg)

- From the moment the box has 3 satellites the first mission will be displayed. 

- A mission screen shows a description of the target location, your distance to that location and the radius of how close you need to be to the location. 

![](/assets/Mission LCD.jpg)

- The closer you get, the more red lights will light up. From the moment you are very close, they will all turn green. 

- If all missions are completed a message stating that will show up. If you want to play again just power off the box and power it back on.

