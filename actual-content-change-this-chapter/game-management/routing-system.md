# routes

## routes.php
The routes.php file says wich route should do what in the slim framework.  
We use controller system this means that for use the routes.php file only says what controller should be called and what funciton within that controller.

## indexcontroller
this controller is responsible for all the routes that do not require a valid login.

| method | page | description |
| :----|:------- | :------------- |
| GET | / | shows home page |
| GET | /about | shows about page |
| GET | [/booking](booking) | shows a form to book a game |
| POST | [/booking](booking) | process the booking and redirects to home |
| GET | /scores | show scores of past games |
| GET | /login | shows a login page |
| POST | /login | process login and redirects to login on failure or the needed page on success |
| GET | /logout | logs you out and redirects to homepage |

## authcontroller
this controller is responsible for all the routes for a game master or team member

| method | page | description |
| :-|:-|:-|
| GET | [/control](controlpanel) | page for game master |
| GET | [/upload](upload) | page for team members |

## apicontroller
This controllers handles everything for the api.
Every route in this controller starts with `/secret`.
It is called secret and not api because we have a api folder in our public folder,   
calling any route that starts with api will look in that folder, and not in the routing system.

| method | page | description |
| :-|:-|:-|
| POST | /creators | endpoint for game creators to upload new games |

## admincontroller

This controller handles general, not game bounded things for the system admin.
All routes in this controller start with `/adminpage`.
To get in any route in this controller you need to enter the key set as `ADMINKEY` from the .env file or from the environment variables.

| method | page | description |
| :-|:-|:-|
| GET | [/](Adminpanel) | page for game master |
| POST | [/acceptbooking](view-all-bookings) | convertes booking into a game and mails the booker |
| POST | [/denyBooking](view-all-bookings) | removes a booking and sends a mail to the booker |
| POST | /deleteGame | deletes a old game from the system |

## gamecontroller

This controller handles game specific things for the system admin.
All routes in this controller start with `/adminpage/editGame/{gameID}` with {gameID} being the 24 characters hex code that represents the ID of the game.

| method | page | description |
| :-|:-|:-|
| GET | [/](edit-games) | displays all the info from the game and shows the buttons to do actions |
| POST | / | redirects to the get version, but this time without the ? at the end of the url |
| POST | [/addScenario](edit-games/scenario) | changes a scenario and returns editgame page |
| POST | [/addTeamNames](edit-games/teamnames) | saves teamnames to the database |


# processing a request

![](/assets/routering1.png)

![](/assets/routering2.png)


