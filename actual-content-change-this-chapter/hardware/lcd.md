## LCD

\# LCD & LEDs



---

\#\#\# Setup



\*\*Connect LCD to mBed:\*\*

\* Connect following pins from the LCD to the mBed:



id  \| LCD \| mBed \| Description

----\|-----\|------\|------------

GND \| 1   \| GND   \| Ground for lcd

VDD \| 2   \| 5V    \| +5V for LCD

CA  \| 3   \| 10K   \| Contrast adjustment

RS  \| 4   \| PTC3  \| Register select

R/W \| 5   \| GND   \| Read/write

E   \| 6   \| PTC2  \| enable

D0  \| 7   \| NC    \| Data 0 \(not connected\)

D1  \| 8   \| NC    \| Data 1 \(not connected\)

D2  \| 9   \| NC    \| Data 2 \(not connected\)

D3  \| 10  \| NC    \| Data 3 \(not connected\)

D4  \| 11  \| PTA2  \| Data 4

D5  \| 12  \| PTB23 \| Data 5

D6  \| 13  \| PTA1  \| Data 6

D7  \| 14  \| PTB9  \| Data 7

VDD \| 15  \| +5V   \| +5V for led

GND \| 16  \| GND   \| Ground for led



\[Datasheet\]\(https://www.sparkfun.com/datasheets/LCD/GDM2004D.pdf\)



\* We make use of the \[TextLCD\]\(https://developer.mbed.org/users/simon/code/TextLCD/\) library





