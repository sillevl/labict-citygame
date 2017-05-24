
---

# **Managing Markers and Dialog Windows**

Manage Google map markers, has been a hard work and difficult. We have had various problems, which we have been resolving throughout the project. We will now make a summary of how evolved, and the final result that we have achieved.

### The first way to add a marker.

First we create a button to manually enter the longitude and latitude.  When we wrote a coordinate,  a marker appeared on the map in the corresponding point. This way to get a marker was a test, because we simply wanted to see the operation of the library that we had  and how to manage it to our liking.

![](/assets/LocationAndLongitude.png)

### The definitive way to add a marker.

It worked, and we wanted to go further. We thought that it would be easier for the user to click on the screen to select the point that the user knew exactly the coordinate \(latitude and longitude\) of the point that he wanted to add. So, we decided when the user click with the right button at one point specific to the map, a marker will appear at the point of the map that was clicked.![](/assets/mapMarker1.png)

### How to add more information about the mission

When we already knew how to correctly add the marker, we think on how to add some kind of information about the mission we wanted to create. We think that the best thing would be that when we clicked with the right mouse button, a pop-up window is opened and all the relevant information had to fill in. This information is:

* Mission Number: it is set automatically by the program.
* Name Mission: Official name of the mission.
* Objectuve: Objective of the mission.
* Position: Latitude and longitude. We obtain this value when we click on the map. The position can change manually.
* Radius: The radius of the marker that you want in each mission.

![](/assets/AddDialogWindow.png)

Add the radio on the map was not an issue, because the library where we are based, had a specific method to add a circle to the map.![](/assets/ExampleRadiusandMap.png)

### Draggable marker and radius

This section has been the most laborious and that more difficulties we found on the markers. But finally we have achieved pretty good results.

First we work on the draggable marker. We assumed a series of difficulties, for example remove the previous marker. But we solve it and now works perfectly. You can click on the marker and drag it to another part of the map. The new position was saved.

The draggable radio was more difficult. Methods that came in the program that we are based, not give us solution to a small bug which today continues in the program. The error is that when we want to change the size of the RADIUS, or move the radio to another location, we have to click inside the circle which is drawn. If we do not click, the operation is not confirmed. We expected that releasing the mouse to make the different variations, you could capture that event, but there is an EventHandler for this action.![](/assets/radius.png)This sequence of images represents the small bug in the radio.

_Everything about this part of the project, is located in a library called "gamecreator.map"_

### Java Classes about Markers and Dialog Window

We can see then in UML format, classes that are directly related to markers and dialog Windows-![](/assets/UMLMARKERS.png)As we can see, these classes mark the behavior of the markers and the missions. There could be a refactoring of the AddLocationDialog and AddObjectiveDialog classes, but we prefer to keep it that way, because it follow the criterion of singular responsibility.

