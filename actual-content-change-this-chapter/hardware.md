# Hardware

The hardware consists out of a few different parts. These can have an input, output or input/output function. Here is a list of all the individual parts with their function.

|       Name       | I/0? |                  Description                  |
|------------------|------|-----------------------------------------------|  
| ARM Processor    |Brain| The brain of the whole project, it handles the input and output of all other components.|
| LoRa Tranceiver  | I/O  | This is the part that sends and receives data to/from the servers. |
| GPS Chip | I | The chip calculates the location of where the case is. |
| Buzzer| O | Makes noises that correspond to different actions. |
| LEDs | O | Gives a visual representation of states in the current program. |
| LCD  | O | Shows the user where to go or what to do. |
| Key | I | A key contact that adds an element of gameplay (eg. find the key) |
| Button | I | Used for input in missions or an UI |
| Keypad | I | Used for input in missions or an UI (eg. enter the code)|
|Battery System | I | Powers the project and also returns it's battery level |

***

In the following parts of "Hardware" we will take a closes look at all these different parts.
***

## ARM Processor

***

## LoRa Tranceiver

***

## GPS Chip

***

## Buzzer

***

## LEDs

***

## LCD

***

## Key

***

## Button

***

## Keypad

***
## Battery System

The projects uses Li-ion batteries which operate at:
* A minimum voltage of 2,8V
* A maximum discharge current of 4400mA
    
The battery management system accommodates these specifications:

* A minimum voltage is provided through the use of a differential             amplifier, the reference voltage is provided by a zener diode.
* A maximum discharge current is safeguarded through the means of a DC-DC boost step-up converter. As this enables us to limit the maximum current, through the use of external passive components.

***


