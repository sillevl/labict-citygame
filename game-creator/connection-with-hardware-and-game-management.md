# Connection with Hardware and Gamemanagement

* ### Introduction

The jason created by our application that contains all necessary information for the game to be created has to be received by Game Management and hardware. To achieve this we chose for a serial connection with the box, and an API connection with Game Management.

* ### Overview

![](/assets/import.png)

In the topbar you get the choice to either upload or connect.

If you choose to upload you wil upload the json file to the Game Management, if you choose to Connect, you will need to connect the box by usb with the pc to send the json to the box.

To accomplish the connectivity with Game Management and Hardware, three dependencies and two classes had to be written, We also added two new buttons in the File menu. The dependencies are OkHttp and OkIO which will be explained in chapter **API**. The third dependency is the communicator which will be explained in chapter **Serial Connection**.



