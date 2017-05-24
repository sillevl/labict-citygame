# Hardware

## Introduction

At the beginning of our semester, we got the introduction for the second project we could work on during our studies of Elektronics-ICT, namely a city game. This is an interactive game that can be played with different teams. Each team needs to complete some missions throughout a city (in this case: the city of Ostend) using gaming boxes. These boxes contain: a processor, a buzzer, 5 LEDS, a LCD-screen, a LoRa Tranceiver, a complete battery system, a GPS chip, a keypad, 2 buttons and a keyswitch. If we put these pieces of hardware correctly together we should be able to communicate with the game master who can see the status of the different teams.

The hardware consists out of a few different parts. These can have an input, output or input/output function. Here is a list of all the individual parts with their function.

| Name | I/0? | Description |
| --- | --- | --- |
| ARM Processor | Brain | The brain of the whole project, it handles the input and output of all other components. |
| LoRa Tranceiver | I/O | This is the part that sends and receives data to/from the servers. |
| GPS Chip | I | The chip calculates the location of where the case is. |
| Buzzer | O | Makes noises that correspond to different actions. |
| LEDs | O | Gives a visual representation of states in the current program. |
| LCD | O | Shows the user where to go or what to do. |
| Key | I | A key contact that adds an element of gameplay \(eg. find the key\) |
| Button | I | Used for input in missions or an UI |
| Keypad | I | Used for input in missions or an UI \(eg. enter the code\) |
| Battery System | I | Powers the project and also returns it's battery level |

---

**In the following parts of "Hardware" we will take a closer look at all these different parts.**

