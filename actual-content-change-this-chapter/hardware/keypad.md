## Keypad

The user should be able to manually enter some codes for certain missions, the keypad will take care of that.

## MCAK304NBWB
![](/assets/keypad_vives.png)

This is the keypad that we use. The product name is MCAK304NBWB, it's cheap and you can easily order it online. It's not hard to connect to the mbed.

## Connection to the mbed
This is a 4 by 3 keypad which means that we need 4 pins for the rows and 3 pins for the columns. You can see the pinouts we used and how the keypad is internally wired up on the image below.

![](/assets/Keypad + pinouts.png)

## Working of the keypad
The keypad works using a matrix system, normally one port would be required to read a digital input into the controller, but we have a lot of digital inputs that have to be read so it would not be recommended to allocate one pin for each of them. This is why a matrix keypad arrangement is used to reduce the pin count. 
When a button is pressed, the corresponding row and columns are short circuited, this will drive the column pin (that was originally high) low and it will drive the row pin (that was originally low) high.

![](/assets/Keypad_working.PNG)

## Specifications of the keypad
![](/assets/specifications_keypad.png)

Read more about this in the datasheet: [Keypad datasheet](http://www.farnell.com/datasheets/1662617.pdf?_ga=2.267866505.681420666.1495444655-1070812418.1494403917)

## Keypad code 
This is the UML schematic of the keypad code made in Lucidchart. It consists out of two parts, the FPointer class which adds callbacks that take and return a 32bit uint32_t data type and the keypad class which can detect which button has been pressed. This solid diamond represents the relationship between the FPointer and Keypad class: a composition (= objects are built from other objects). 

![](/assets/Keypad_UML.png)

Here you can find the library I used for the keypad: [Keypad Library](https://developer.mbed.org/users/yoonghm/code/keypad/#da060f8c03e8)