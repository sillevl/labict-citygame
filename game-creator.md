# Game Creator

## Introduction

Game Creator has been designed and developed as an application to create the different games that belong to "VIVES CITY GAME". The main functions of this application are:

* Create a new game at a specific point on the map.
* Save and manage all the information related to the missions of orderly and clear.
* Create a path specified to get moving in a mission to another.
* Open a previously saved game.
* Save the game that we created \(the information will be in JSON format\)
* Transmit the information of the game \(JSON file\) to the hardware and Game Management.

## How to use the application

### Welcome Scene

![](/assets/WelcomScene.png)The first step that we need to do to start the application is click on the button "File" which will only have one option available. That option is New, it let's you create a new game and lets you enter the following screen of the application.

![](/assets/startscreen topbar.png)

### Gamescene

After we press the option to make a new game, we will be entering the next screen of the application. In this Gamescene screen the user will spent most of its time setting up the game, choosing their team name and adding a description of the game.

![](/assets/gamescene.png)In this screen you have the option to choose with how many teams you want to play, due to design decisions later down the project, there will only be the option to choose for 1 team. The code which makes it possible for the game to be played with up to three teams is still in the project but unused.

![](/assets/number of teams.png)

After having set the number of teams from 0 to 1, a new button will appear on the screen. When this mission button is pressed a map will be loaded in a seperate window. The use and functions of this map will be explained later on in the chapter **Creating Games**.

![](/assets/gamescene 2.png)

In this Gamescene screen the Topbar will have unlocked all its options, each of these options do one of the following things:

* New: Create a new GamePacket for each Team and reset any previously made changes
* Open: Open a collection of previously-created games
* Save as: Create the JSON file with all information about the games
* Upload: Upload the JSON file to the Game Management
* Connect: Sends the JSON file to the Hardware Box \(not fully implemented yet\)

![](/assets/MenuOptions.png)

