# Controlpanel

## Intro

At this webpage the "gamemaster" can view the gameprogress and locate where the teams are at the moment.

## Overview

![](/assets/cp_overview.png)

## Connections with the database

#### When?

1. Game loading  -&gt; Load the game from the database with the correct unique game id \(oid\).
2. Game check    -&gt; Check if the game is played before.
3. Game update  -&gt; Send the mission info after mission is completed.

#### How can this be dynamic and secure?

In our project we're using node.js and websockets.

NodeJS is an  Event-driven I/O server-side JavaScript environment.  
Because this script runs on the server, the user will never see critical information \(passwords for the database\).

Websockets makes it possible to send new data to the browser without refreshing the page.

## Notifications

To get the attention of the gamemaster when a mission is finished there is an alert-sound and a pop-up shows up in the bottom.

![](/assets/cp_notification.png)

## Game UML

The game creator puts a JSON game in the database.  
When a file loaded in we converts it directly to a game object because of object oriented programming.

![](/assets/cp_game_uml.png)

